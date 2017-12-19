---
UID: NF.ntifs.IoIsOperationSynchronous
title: IoIsOperationSynchronous function
author: windows-driver-content
description: The IoIsOperationSynchronous routine determines whether a given IRP represents a synchronous or asynchronous I/O request.
old-location: ifsk\ioisoperationsynchronous.htm
old-project: ifsk
ms.assetid: b233dfab-6a99-4f2f-930e-cafd01dc4bb5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IoIsOperationSynchronous
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoIsOperationSynchronous
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
req.irql: Any level
---

# IoIsOperationSynchronous function



## -description
The <b>IoIsOperationSynchronous</b> routine determines whether a given IRP represents a synchronous or asynchronous I/O request. 



## -syntax

````
BOOLEAN IoIsOperationSynchronous(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

Pointer to the IRP for the operation. 


## -returns
<b>IoIsOperationSynchronous</b> returns <b>TRUE</b> if the operation is synchronous, otherwise <b>FALSE</b>. 


## -remarks
<b>IoIsOperationSynchronous</b> determines whether a given IRP requests a synchronous or asynchronous I/O operation, according to the following conditions: 

If the IRP requests asynchronous paging I/O, the operation is asynchronous, even if one of the other conditions is true. 

If the IRP requests synchronous paging I/O, the operation is synchronous. 

If the file object was opened for synchronous I/O, the operation is synchronous. 

If the IRP_SYNCHRONOUS_API flag is set in the IRP, the operation is synchronous. This flag is set for operations, such as <a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a> and <a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>, that are always synchronous, even when performed on a file object that was opened for asynchronous I/O. 

If none of the above conditions is true, the operation is asynchronous. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="kernel.iocreatefile">IoCreateFile</a>
</dt>
<dt>
<a href="ifsk.iocreatefileex">IoCreateFileEx</a>
</dt>
<dt>
<a href="ifsk.iocreatefilespecifydeviceobjecthint">IoCreateFileSpecifyDeviceObjectHint</a>
</dt>
<dt>
<a href="kernel.irp">IRP</a>
</dt>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoIsOperationSynchronous routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

