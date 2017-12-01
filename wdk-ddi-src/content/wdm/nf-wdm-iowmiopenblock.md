---
UID: NF.wdm.IoWMIOpenBlock
title: IoWMIOpenBlock
author: windows-driver-content
description: The IoWMIOpenBlock routine opens the WMI data block object for the specified WMI class.
old-location: kernel\iowmiopenblock.htm
old-project: kernel
ms.assetid: c23d1861-59df-4bd4-a005-173ccac53049
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IoWMIOpenBlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h. The WMIGUID_XXX values are declared in Wmistr.h. To use them, include Wmistr.h.
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoWMIOpenBlock
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# IoWMIOpenBlock function



## -description
<p>The <b>IoWMIOpenBlock</b> routine opens the WMI data block object for the specified WMI class.</p>


## -syntax

````
NTSTATUS IoWMIOpenBlock(
  _In_  GUID  *DataBlockGuid,
  _In_  ULONG DesiredAccess,
  _Out_ PVOID *DataBlockObject
);
````


## -parameters
<dl>

### -param <i>DataBlockGuid</i> [in]

<dd>
<p>Specifies the GUID for WMI class.</p>
</dd>

### -param <i>DesiredAccess</i> [in]

<dd>
<p>Specifies the desired access rights to the data block object. The caller must have particular access rights to perform certain operations. </p>
<p>The following is a description of each access right bit and the operations it allows:</p>
<p></p>
<dl>

### -param <a id="WMIGUID_EXECUTE"></a><a id="wmiguid_execute"></a>WMIGUID_EXECUTE

<dd>
<p>The data block object can be used to run WMI class methods. This flag must be set to use <a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a> on the data block object. </p>
</dd>

### -param <a id="WMIGUID_NOTIFICATION"></a><a id="wmiguid_notification"></a>WMIGUID_NOTIFICATION

<dd>
<p>The data block object can be used to register event notification callbacks. This flag must be set to use <a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a>, and can only be used for WMI event blocks. Callers that specify this flag must also specify the SYNCHRONIZE flag.</p>
</dd>

### -param <a id="WMIGUID_QUERY"></a><a id="wmiguid_query"></a>WMIGUID_QUERY

<dd>
<p>The data block object can be used to query WMI class properties. This flag must be set to use any of the <b>IoWMIQuery<i>Xxx</i></b> routines on the data block object. </p>
</dd>

### -param <a id="WMIGUID_SET"></a><a id="wmiguid_set"></a>WMIGUID_SET

<dd>
<p>The data block object can be used to set WMI class properties. This flag must be set to use any of the <b>IoWMISet<i>Xxx</i></b> routines on the data block object. </p>
</dd>
</dl>
</dd>

### -param <i>DataBlockObject</i> [out]

<dd>
<p>Pointer to a memory location where the routine returns a pointer to the data block object.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.</p>

## -remarks
<p>The caller uses <b>IoWMIOpenBlock</b> to create a data block object for the specified WMI class GUID. Subsequently, the caller can use the data block object to read or write WMI class properties, run WMI class methods, and register callbacks for WMI events.</p>

<p>Use the <b>IoWMIQuery<i>Xxx</i></b> and <b>IoWMISet<i>Xxx</i></b> routines to read and write WMI class properties. Use <a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a> to run WMI class methods, and use <a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a> to register a WMI event notification callback.</p>

<p>Use <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> to close the data block object once it is no longer needed.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows XP and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (Include Wdm.h, Ntddk.h, or Ntifs.h. The WMIGUID_XXX values are declared in Wmistr.h. To use them, include Wmistr.h.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiqueryalldata.md">IoWMIQueryAllData</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiqueryalldatamultiple.md">IoWMIQueryAllDataMultiple</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiquerysingleinstance.md">IoWMIQuerySingleInstance</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiquerysingleinstancemultiple.md">IoWMIQuerySingleInstanceMultiple</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmisetsingleinstance.md">IoWMISetSingleInstance</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIOpenBlock routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
