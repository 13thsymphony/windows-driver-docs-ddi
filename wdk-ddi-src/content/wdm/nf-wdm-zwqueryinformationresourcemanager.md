---
UID: NF.wdm.ZwQueryInformationResourceManager
title: ZwQueryInformationResourceManager function
author: windows-driver-content
description: The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object.
old-location: kernel\zwqueryinformationresourcemanager.htm
old-project: kernel
ms.assetid: 6faeb410-486e-4b79-b942-62d16039d24b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwQueryInformationResourceManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwQueryInformationResourceManager,NtQueryInformationResourceManager
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# ZwQueryInformationResourceManager function



## -description
The <b>ZwQueryInformationResourceManager</b> routine retrieves information about a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.



## -syntax

````
NTSTATUS ZwQueryInformationResourceManager(
  _In_      HANDLE                            ResourceManagerHandle,
  _In_      RESOURCEMANAGER_INFORMATION_CLASS ResourceManagerInformationClass,
  _Out_     PVOID                             ResourceManagerInformation,
  _In_      ULONG                             ResourceManagerInformationLength,
  _Out_opt_ PULONG                            ReturnLength
);
````


## -parameters

### -param ResourceManagerHandle [in]

A handle to a resource manager object that was obtained by a previous call to <a href="kernel.zwcreateresourcemanager">ZwCreateResourceManager</a> or <a href="kernel.zwopenresourcemanager">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object.


### -param ResourceManagerInformationClass [in]

A <a href="kernel.resourcemanager_information_class">RESOURCEMANAGER_INFORMATION_CLASS</a>-typed value that specifies the information to retrieve. This value must be <b>ResourceManagerBasicInformation</b>.


### -param ResourceManagerInformation [out]

A pointer to a caller-allocated <a href="kernel.resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a> structure that receives information from <b>ZwQueryInformationResourceManager</b>.


### -param ResourceManagerInformationLength [in]

The length, in bytes, of the buffer that the <i>ResourceManagerInformation</i> parameter points to.


### -param ReturnLength [out, optional]

A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>ResourceManagerInformation</i> buffer. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>ZwQueryInformationResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The specified handle is not a handle to a resource manager object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>The <i>ResourceManagerInformationClass</i> parameter's value is invalid.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer size that the <i>ResourceManagerInformationLength </i>parameter specifies is smaller than the RESOURCEMANAGER_BASIC_INFORMATION structure.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer size that the <i>ResourceManagerInformationLength </i>parameter specifies is too small to receive all the variable-length information that is available.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the resource manager object.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
For more information about the <b>ZwQueryInformationResourceManager</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

<b>NtQueryInformationResourceManager</b> and <b>ZwQueryInformationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available in Windows Vista and later operating system versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="kernel.resourcemanager_information_class">RESOURCEMANAGER_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwcreateresourcemanager">ZwCreateResourceManager</a>
</dt>
<dt>
<a href="kernel.zwopenresourcemanager">ZwOpenResourceManager</a>
</dt>
<dt>
<a href="kernel.zwrecoverresourcemanager">ZwRecoverResourceManager</a>
</dt>
<dt>
<a href="kernel.zwsetinformationresourcemanager">ZwSetInformationResourceManager</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryInformationResourceManager routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

