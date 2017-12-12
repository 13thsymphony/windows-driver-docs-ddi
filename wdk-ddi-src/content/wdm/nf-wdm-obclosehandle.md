---
UID: NF.wdm.ObCloseHandle
title: ObCloseHandle function
author: windows-driver-content
description: The ObCloseHandle routine closes an object handle.
old-location: kernel\obclosehandle.htm
old-project: kernel
ms.assetid: 15D6A09F-2AEC-431F-91F4-D1571DB56E81
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ObCloseHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObCloseHandle
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# ObCloseHandle function



## -description
The <b>ObCloseHandle</b> routine closes an object handle.



## -syntax

````
NTSTATUS ObCloseHandle(
  _In_ HANDLE          Handle,
  _In_ KPROCESSOR_MODE PreviousMode
);
````


## -parameters

### -param Handle [in]

A handle to a system-supplied object of any type.


### -param PreviousMode [in]

Specifies the previous processor mode of the thread that opened the handle. To close a <a href="wdkgloss.k#wdkgloss.kernel_handle#wdkgloss.kernel_handle"><i>kernel handle</i></a>, set this parameter to <b>KernelMode</b>. To close a <i>user handle</i>, set this parameter to <b>UserMode</b>. For more information about these two handle types, see Remarks.


## -returns
<b>ObCloseHandle</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following NTSTATUS codes.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><i>Handle</i> is not a valid handle.
<dl>
<dt><b>STATUS_HANDLE_NOT_CLOSABLE</b></dt>
</dl>The calling thread does not have permission to close the handle.

 


## -remarks
A kernel-mode driver calls <b>ObCloseHandle</b> to close a handle to any type of object that is created by the Windows kernel. A driver must close every handle that it opens as soon as the handle is no longer required.

After <b>ObCloseHandle</b> closes an object's handle, the caller must treat the handle as invalid and avoid using the handle to access the object. However, other handles might remain open on the same object. During an <b>ObCloseHandle</b> call, the system decrements the handle count for the object and checks whether the object can be deleted. The system does not delete the object until all of the object's handles are closed and all reference-counted pointers to the object are released.

The <i>PreviousMode</i> parameter specifies whether the handle to be closed is a kernel handle or a user handle. To close a kernel handle, set <i>PreviousMode</i> to <b>KernelMode</b>. To close a user handle, set <i>PreviousMode</i> to <b>UserMode</b>.

A kernel handle is a handle that is opened by a system thread, or by a kernel-mode driver that assigns the OBJ_KERNEL_HANDLE attribute to the handle. (For example, see the description of OBJ_KERNEL_HANDLE in <a href="kernel.zwcreatefile">ZwCreateFile</a>.) If a kernel-mode driver opens a handle for its private use, and this driver runs in the context of a user-mode thread, the driver must open the handle with the OBJ_KERNEL_HANDLE attribute. This attribute ensures that the handle is inaccessible to user-mode applications.

A user handle is a handle that is opened by a user-mode application, or by a kernel-mode driver that runs in the context of a user-mode thread but that does not open the handle with the OBJ_KERNEL_HANDLE attribute. If a driver creates a user handle to be used by a user-mode application, but an error occurs that requires the driver to close the handle on behalf of the application, the driver can call <b>ObCloseHandle</b> to close the handle.

The <b>ZwClose</b> routine is similar to <b>ObCloseHandle</b> but can close only kernel handles. The call <b>ZwClose</b>(<i>hObject</i>), which closes kernel handle <i>hObject</i>, has the same effect as the call <b>ObCloseHandle</b>(<i>hObject</i>, <b>KernelMode</b>). For more information about closing a kernel handle, see <a href="kernel.zwclose">ZwClose</a>.

To determine whether a handle is a kernel handle or a user handle,  a driver that receives a handle  can call the <a href="kernel.exgetpreviousmode">ExGetPreviousMode</a> routine. Or, the driver can read the <b>RequestorMode</b> field from the <a href="kernel.irp">IRP</a> structure that describes the I/O request. The I/O manager sets the <b>RequestorMode</b> field to the previous processor mode of the thread that requested the I/O operation.

Callers of <b>ObCloseHandle</b> should not assume that this routine automatically waits for all pending I/O operations to complete before it returns.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

<b>ObCloseHandle</b> is not declared in a header file prior to Windows 7. To use this routine in your driver, include the following function declaration in your driver code:


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
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exgetpreviousmode">ExGetPreviousMode</a>
</dt>
<dt>
<a href="kernel.irp">IRP</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObCloseHandle routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

