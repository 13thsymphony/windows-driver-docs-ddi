---
UID: NF.wdm.ClfsReserveAndAppendLog
title: ClfsReserveAndAppendLog
author: windows-driver-content
description: The ClfsReserveAndAppendLog routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically.
old-location: kernel\clfsreserveandappendlog.htm
old-project: kernel
ms.assetid: e3ffbf18-151b-42da-8fc1-ae07c152738c
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ClfsReserveAndAppendLog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsReserveAndAppendLog
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ClfsReserveAndAppendLog function



## -description
<p>The <b>ClfsReserveAndAppendLog</b> routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically.</p>


## -syntax

````
NTSTATUS ClfsReserveAndAppendLog(
  _In_      PVOID             pvMarshalContext,
  _In_opt_  PCLFS_WRITE_ENTRY rgWriteEntries,
  _In_      ULONG             cWriteEntries,
  _In_opt_  PCLFS_LSN         plsnUndoNext,
  _In_opt_  PCLFS_LSN         plsnPrevious,
  _In_      ULONG             cReserveRecords,
  _Inout_   PLONGLONG         rgcbReservation,
  _In_      ULONG             fFlags,
  _Out_opt_ PCLFS_LSN         plsn
);
````


## -parameters
<dl>

### -param <i>pvMarshalContext</i> [in]

<dd>
<p>A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.</p>
</dd>

### -param <i>rgWriteEntries</i> [in, optional]

<dd>
<p>A pointer to an array of <a href="kernel.clfs_write_entry">CLFS_WRITE_ENTRY</a> structures, each of which holds a pointer to a buffer of data that will become part of the record that is appended to the log. This parameter can be <b>NULL</b> if <i>cWriteEntries</i> is zero.</p>
</dd>

### -param <i>cWriteEntries</i> [in]

<dd>
<p>The number of elements in the array pointed to by <i>rgWriteEntries</i>. This parameter must be zero if <i>rgWriteEntries</i> is <b>NULL</b>.</p>
</dd>

### -param <i>plsnUndoNext</i> [in, optional]

<dd>
<p>A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that supplies the undo-next LSN of the record to be appended.</p>
</dd>

### -param <i>plsnPrevious</i> [in, optional]

<dd>
<p>A pointer to a CLFS_LSN structure that supplies the previous LSN of the record to be appended.</p>
</dd>

### -param <i>cReserveRecords</i> [in]

<dd>
<p>The number of elements in the array pointed to by <i>rgcbReservation</i>. This parameter must be zero if <i>rgcbReservation</i> is <b>NULL</b> or the CLFS_FLAG_USE_RESERVATION flag of <i>fFlags</i> is set.</p>
</dd>

### -param <i>rgcbReservation</i> [in, out]

<dd>
<p>A pointer to an array of LONGLONG-typed variables. The caller sets each element of the array to the size, in bytes, of a record that must have space reserved for it. On return, each array element receives that actual size of the space reserved for the record. This includes the space required for headers and alignment. If the reservation value is negative, a reserved record that most nearly matches the absolute value of the provided negative value will be freed. This parameter can be <b>NULL</b> if <i>cReserveRecords</i> is zero and must be <b>NULL</b> if the CLFS_FLAG_USE_RESERVATION flag of <i>fFlags</i> is set.</p>
</dd>

### -param <i>fFlags</i> [in]

<dd>
<p>This parameter can be zero or any combination of the following flags.</p>
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>CLFS_FLAG_FORCE_APPEND</p>
</td>
<td>
<p>After the current record is appended to a log I/O block, the block is queued, in LSN sequence, to stable storage. This flag provides no guarantee that the record is forced to stable storage (see CLFS_FLAG_FORCE_FLUSH).</p>
</td>
</tr>
<tr>
<td>
<p>CLFS_FLAG_FORCE_FLUSH</p>
</td>
<td>
<p>After the current record is appended to a log I/O block, the block is forced to stable storage.</p>
</td>
</tr>
<tr>
<td>
<p>CLFS_FLAG_USE_RESERVATION</p>
</td>
<td>
<p>The current record is placed in reserved space in a log I/O block within the marshalling area. The number of reserved records in the marshalling area is reduced by one. If this flag is set, <i>cReserveRecords</i> must be zero and <i>rgcbReservation</i> must be <b>NULL</b>.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>plsn</i> [out, optional]

<dd>
<p>A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that receives the LSN of the appended record. This parameter can be <b>NULL</b> if <i>cWriteEntries</i> is zero.</p>
</dd>
</dl>

## -returns
<p><b>ClfsReserveAndAppendLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.</p>

## -remarks
<p>The <b>ClfsReserveAndAppendLog</b> routine changes its fundamental behavior based on the presence of optional parameters and the state of the CLFS_USE_RESERVATION flag. The following table summarizes common scenarios.</p>

<p><i>cWriteEntries</i> = 0.</p>

<p><i>rgWriteEntries</i> = <b>NULL</b>.</p>

<p><i>plsn</i> = <b>NULL</b>.</p>

<p>Reserves space for a set of records, but does not append the records to the marshalling area. The <i>rgcbReservation</i> parameter gives the size of the data portion of each record that needs space reserved.</p>

<p><i>cWriteEntries</i> &gt; 0.</p>

<p><i>rgWriteEntries</i> is not <b>NULL</b>.</p>

<p><i>plsn</i> is not <b>NULL</b>.</p>

<p><i>cReserveRecords</i> = 0.</p>

<p><i>rgcbReservation</i> is <b>NULL</b>.</p>

<p>CLFS_USE_RESERVATION is set.</p>

<p>Appends a record to the marshalling area by using space that has already been reserved. Reduces the number of reserved record spaces by one.</p>

<p>CLFS_USE_RESERVATION is cleared.</p>

<p>Appends a record to the marshalling area by reserving new space. Leaves the number of reserved record spaces unchanged.</p>

<p><i>cReserveRecords</i> &gt; 0.</p>

<p>rgcbReservation is not <b>NULL</b>.</p>

<p>CLFS_USE_RESERVATION flag is cleared.</p>

<p>Appends a record to the marshalling area by reserving new space. Also reserves space for a set of records that are not appended at this time. The <i>rgcbReservation</i> parameter gives the size of each record that needs space reserved. Increases the number of reserved record spaces by the value of <i>cReserveRecords</i>.</p>

<p>Calling <b>ClfsReserveAndAppendLog</b> is equivalent to calling <a href="..\wdm\nf-wdm-clfsreserveandappendlogaligned.md">ClfsReserveAndAppendLogAligned</a> with the <i>cbEntryAlignment</i> parameter set to one.</p>

<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfs_lsn">CLFS_LSN</a>
</dt>
<dt>
<a href="kernel.clfs_write_entry">CLFS_WRITE_ENTRY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfsreserveandappendlogaligned.md">ClfsReserveAndAppendLogAligned</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsReserveAndAppendLog routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
