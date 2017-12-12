---
UID: NF.wdm.ClfsReadLogRecord
title: ClfsReadLogRecord function
author: windows-driver-content
description: The ClfsReadLogRecord routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream.
old-location: kernel\clfsreadlogrecord.htm
old-project: kernel
ms.assetid: 9bc64d00-3590-4bc2-aa1f-0d50bb0e628d
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ClfsReadLogRecord
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
req.alt-api: ClfsReadLogRecord
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
req.product: Windows 10 or later.
---

# ClfsReadLogRecord function



## -description
The <b>ClfsReadLogRecord</b> routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream.



## -syntax

````
NTSTATUS ClfsReadLogRecord(
  _In_    PVOID             pvMarshalContext,
  _Inout_ PCLFS_LSN         plsnFirst,
  _In_    CLFS_CONTEXT_MODE peContextMode,
  _Out_   PVOID             *ppvReadBuffer,
  _Out_   PULONG            pcbReadBuffer,
  _Out_   PCLFS_RECORD_TYPE peRecordType,
  _Out_   PCLFS_LSN         plsnUndoNext,
  _Out_   PCLFS_LSN         plsnPrevious,
  _Out_   PVOID             *ppvReadContext
);
````


## -parameters

### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="kernel.clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.


### -param plsnFirst [in, out]

A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that supplies the LSN of the target record in the log.


### -param peContextMode [in]

A value from the <a href="kernel.clfs_context_mode">CLFS_CONTEXT_MODE</a> enumeration that specifies the initial mode (ClfsContextUndoNext, ClfsContextPrevious, or ClfsContextForward) of the read context returned in <i>ppvReadContext</i>.


### -param ppvReadBuffer [out]

A pointer to a variable that receives a pointer to the data buffer of the target record.


### -param pcbReadBuffer [out]

A pointer to a ULONG-typed variable that receives the size, in bytes, of the buffer pointed to by *<i>ppvReadBuffer</i>. This is the length of the data buffer of the target record.


### -param peRecordType [out]

A pointer to a variable of type CLFS_RECORD_TYPE that receives one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>ClfsDataRecord</b>

</td>
<td>
The target record is a data record.

</td>
</tr>
<tr>
<td>
<b>ClfsRestartRecord</b>

</td>
<td>
The target record is a restart record.

</td>
</tr>
</table>
 


### -param plsnUndoNext [out]

A pointer to a <b>CLFS_LSN</b> structure that receives the undo-next LSN of the target record.


### -param plsnPrevious [out]

A pointer to a <b>CLFS_LSN</b> structure that receives the previous LSN of the target record.


### -param ppvReadContext [out]

A pointer to a variable that receives a pointer to an opaque read context. The client repeatedly passes this context to  <a href="kernel.clfsreadnextlogrecord">ClfsReadNextLogRecord</a> to read the remaining records in a sequence. After the client has read all the records in the sequence, it calls <a href="kernel.clfsterminatereadlog">ClfsTerminateReadLog</a> to free the read context.


## -returns
<b>ClfsReadLogRecord</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
You must call <b>ClfsTerminateReadLog</b> when you have finished using the read context in order to avoid a memory leak.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

For information about reading records from CLFS streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560785">Reading Data Records from a CLFS Stream</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560786">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfsreadnextlogrecord">ClfsReadNextLogRecord</a>
</dt>
<dt>
<a href="kernel.clfsterminatereadlog">ClfsTerminateReadLog</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsReadLogRecord routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

