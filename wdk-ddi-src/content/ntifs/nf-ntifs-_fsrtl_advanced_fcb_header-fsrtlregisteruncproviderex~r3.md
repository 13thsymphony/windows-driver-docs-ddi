---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlRegisterUncProviderEx~r3
title: FsRtlRegisterUncProviderEx function
author: windows-driver-content
description: The FsRtlRegisterUncProviderEx routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).
old-location: ifsk\fsrtlregisteruncproviderex.htm
old-project: ifsk
ms.assetid: 5b7302c1-2f31-4b9f-bddb-7b35bbee4a2c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlRegisterUncProviderEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlRegisterUncProviderEx
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlRegisterUncProviderEx function



## -description
The <b>FsRtlRegisterUncProviderEx</b> routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP).



## -syntax

````
NTSTATUS FsRtlRegisterUncProviderEx(
  _Out_ PHANDLE         MupHandle,
  _In_  PUNICODE_STRING RedirDevName,
  _In_  PDEVICE_OBJECT  DeviceObject,
  _In_  ULONG           Flags
);
````


## -parameters

### -param MupHandle [out]

A pointer to a location in which to return a MUP handle to be used when calling <a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a> to deregister the network redirector. The returned handle is valid only if <b>FsRtlRegisterUncProviderEx</b> returns STATUS_SUCCESS.


### -param RedirDevName [in]

A pointer to a Unicode string that contains the device name of the network redirector. MUP uses this device name to create a symbolic link in the Object Manager namespace whose target is \Device\Mup.


### -param DeviceObject [in]

A pointer to an unnamed device object that represents the network redirector. 


### -param Flags [in]

A bitmask that indicates features supported by the network redirector. A network redirector sets a bit to indicate that a feature is supported. The <i>Flags</i> parameter has two options: 

<dl>
<dd>
FSRTL_UNC_PROVIDER_FLAGS_MAILSLOTS_SUPPORTED

The network redirector supports mailslots. This option is normally reserved for use by the Microsoft SMB redirector.

</dd>
<dd>
FSRTL_UNC_PROVIDER_FLAGS_CSC_ENABLED

The network redirector supports offline access using client-side caching.

</dd>
</dl>

## -returns
<b>FsRtlRegisterUncProviderEx</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The requester mode of the IRP that is sent to MUP was not from kernel mode. 
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>An access violation occurred when attempting access to the MUP device. 
<dl>
<dt><b>STATUS_DATATYPE_MISALIGNMENT</b></dt>
</dl>There was a misalignment of data. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There were insufficient resources available to allocate memory for buffers.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A request was made to register a known provider that was already registered. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>RedirDevName</i> parameter was invalid because the length of <i>RedirDevName</i> was zero. 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>An object type mismatch was encountered with the <i>DeviceObject</i> parameter. 

 


## -remarks
A network redirector must register with the multiple UNC provider (MUP) to handle Universal Naming Convention (UNC) names. MUP is a kernel-mode component responsible for channeling all remote file system accesses using a Universal Naming Convention (UNC) name to a network redirector (the UNC provider) that is capable of handling the remote file system requests. MUP is involved when a UNC path is used by an application as illustrated by the following example that could be executed from a command line: 

MUP is not involved during an operation that creates a mapped drive letter (the "NET USE" command, for example). This operation is handled by the multiple provider router (MPR) and a user-mode WNet provider DLL for the network redirector. However, a user-mode WNet provider DLL might communicate directly with a kernel-mode network redirector driver during this operation.

For network redirectors that conform to the Windows Vista redirector model, MUP is involved even when a mapped network drive is used. File operations performed on the mapped drive go through MUP to the network redirector. Note that in this case, MUP simply passes the operation to the network redirector that is involved.

<b>FsRtlRegisterUncProviderEx</b> sends a private file system control (FSCTL) to MUP to perform the registration. 

The device name specified in the <i>RedirDevName</i> parameter in the call to <b>FsRtlRegisterUncProviderEx</b> becomes a symbolic link to \device\Mup in the object manager namespace. Also, an open request of the device name, <i>RedirDevName</i>, will route itself to the actual network redirector device object pointed to by the <i>DeviceObject</i> parameter. 

Network redirectors that call <b>FsRtlRegisterUncProviderEx</b> must not register themselves as a file system (network redirectors must not call <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>). Network mini-redirectors that use the Windows Vista RDBSS (dynamic or static linking) will not be registered as a file system.

File objects on the remote file system stack owned by a network redirector that conforms to the Windows Vista redirector model resolve to MUP. So <a href="..\ntifs\nf-ntifs-iogetdeviceattachmentbaseref.md">IoGetDeviceAttachmentBaseRef</a> returns the device object for MUP, not the network redirector that owns the file object. However, the content of the file object is still owned by the network redirector. 

The ProviderOrder registry value determines the order in which MUP issues prefix resolution requests to individual network redirectors. This order can be changed dynamically without a reboot. This registry value is located under the following registry key: 

Only one network provider on a system can support mailslots. So the FSRTL_UNC_PROVIDER_FLAGS_MAILSLOTS_SUPPORTED option in the <i>Flags</i> parameter is normally only set for the Microsoft SMB redirector.

To deregister a UNC provider, use <a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a> and pass the <i>MupHandle</i> parameter.

If a driver registers as a local disk file system (by calling <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> with the <i>DeviceType</i> parameter set to FILE_DEVICE_DISK_FILE_SYSTEM), the driver must not call <b>FsRtlRegisterUncProviderEx</b> to register as a UNC provider with MUP.

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>



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
This routine is available on Windows Vista and later versions. 

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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlcancellablewaitforsingleobject.md">FsRtlCancellableWaitForSingleObject</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md">FsRtlDeregisterUncProvider</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>
</dt>
<dt>
<a href="..\ntifs\ni-ntifs-ioctl_redir_query_path_ex.md">IOCTL_REDIR_QUERY_PATH_EX</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iogetdeviceattachmentbaseref.md">IoGetDeviceAttachmentBaseRef</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlRegisterUncProviderEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

