---
UID: NF.wdm.ZwCreateResourceManager
title: ZwCreateResourceManager function
author: windows-driver-content
description: The ZwCreateResourceManager routine creates a resource manager object.
old-location: kernel\zwcreateresourcemanager.htm
old-project: kernel
ms.assetid: 4812eeb4-134f-4ecb-870b-dbab04c1137b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ZwCreateResourceManager
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
req.alt-api: ZwCreateResourceManager,NtCreateResourceManager
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

# ZwCreateResourceManager function



## -description
The <b>ZwCreateResourceManager</b> routine creates a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -syntax

````
NTSTATUS ZwCreateResourceManager(
  _Out_    PHANDLE            ResourceManagerHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     HANDLE             TmHandle,
  _In_opt_ LPGUID             ResourceManagerGuid,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ ULONG              CreateOptions,
  _In_opt_ PUNICODE_STRING    Description
);
````


## -parameters

### -param ResourceManagerHandle [out]

A pointer to a caller-allocated variable that receives a handle to the new resource manager object if the call to <b>ZwCreateResourceManager</b> is successful.

### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the resource manager object. In addition to the access rights that are defined for all kinds of objects (see <b>ACCESS_MASK</b>), the caller can specify any of the following access right flags for resource manager objects:
<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Allows the caller to</th>
</tr>
<tr>
<td>
RESOURCEMANAGER_ENLIST
</td>
<td>
Enlist in transactions (see <a href="kernel.zwcreateenlistment">ZwCreateEnlistment</a>). 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_GET_NOTIFICATION
</td>
<td>
Receive notifications about the transactions that are associated with this resource manager (see <a href="kernel.zwgetnotificationresourcemanager">ZwGetNotificationResourceManager</a>). 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_REGISTER_PROTOCOL
</td>
<td>
Not used. 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_QUERY_INFORMATION
</td>
<td>
Query information about the resource manager (see <a href="kernel.zwqueryinformationresourcemanager">ZwQueryInformationResourceManager</a>). 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_SET_INFORMATION
</td>
<td>
Not used. 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_RECOVER
</td>
<td>
Recover the resource manager (see <a href="kernel.zwrecoverresourcemanager">ZwRecoverResourceManager</a>). 
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_COMPLETE_PROPAGATION
</td>
<td>
Not used. 
</td>
</tr>
</table>
 
Alternatively, you can specify one or more of the following generic <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> flags. (The STANDARD_RIGHTS_<i>Xxx</i> flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table. The following table shows how generic access rights correspond to specific access rights. 
<table>
<tr>
<th>Generic access right</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
RESOURCEMANAGER_GENERIC_READ
</td>
<td>
STANDARD_RIGHTS_READ, RESOURCEMANAGER_QUERY_INFORMATION, and SYNCHRONIZE
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_GENERIC_WRITE
</td>
<td>
STANDARD_RIGHTS_WRITE, RESOURCEMANAGER_SET_INFORMATION, RESOURCEMANAGER_RECOVER, RESOURCEMANAGER_ENLIST, RESOURCEMANAGER_GET_NOTIFICATION, RESOURCEMANAGER_REGISTER_PROTOCOL, RESOURCEMANAGER_COMPLETE_PROPAGATION, and SYNCHRONIZE
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_GENERIC_EXECUTE
</td>
<td>
STANDARD_RIGHTS_EXECUTE, RESOURCEMANAGER_RECOVER, RESOURCEMANAGER_ENLIST, RESOURCEMANAGER_GET_NOTIFICATION, RESOURCEMANAGER_COMPLETE_PROPAGATION, and SYNCHRONIZE
</td>
</tr>
<tr>
<td>
RESOURCEMANAGER_ALL_ACCESS
</td>
<td>
STANDARD_RIGHTS_REQUIRED, RESOURCEMANAGER_GENERIC_READ, RESOURCEMANAGER_GENERIC_WRITE, and RESOURCEMANAGER_GENERIC_EXECUTE
</td>
</tr>
</table>
 

### -param TmHandle [in]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> that was obtained by a previous all to <a href="kernel.zwcreatetransactionmanager">ZwCreateTransactionManager</a> or <a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>. 

### -param ResourceManagerGuid [in, optional]

A pointer to a GUID that KTM will use to identify the resource manager. If this pointer is <b>NULL</b>, KTM generates a GUID.

### -param ObjectAttributes [in, optional]

A pointer to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.

### -param CreateOptions [in, optional]

Optional object creation flags. The following table contains the available flags, which are defined in Ktmtypes.h. 
<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RESOURCE_MANAGER_COMMUNICATION
</td>
<td>
For internal use only. 
</td>
</tr>
<tr>
<td>
RESOURCE_MANAGER_VOLATILE
</td>
<td>
The caller will manage volatile resources. It will be non-persistent and will not perform recovery. 
</td>
</tr>
</table>
 
This parameter is optional and can be zero. 

### -param Description [in, optional]

A pointer to a caller-supplied <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a NULL-terminated string. The string provides a description of the resource manager. KTM stores a copy of the string and includes the string in messages that it writes to the log stream. The maximum string length is MAX_RESOURCEMANAGER_DESCRIPTION_LENGTH. This parameter is optional and can be <b>NULL</b>. 

## -returns
<b>ZwCreateResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The handle that <i>TmHandle</i> specifies is not a handle to a transaction object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The handle that <i>TmHandle</i> specifies is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the specified transaction manager object.
<dl>
<dt><b>STATUS_TRANSACTION_OBJECT_EXPIRED</b></dt>
</dl>The handle that <i>TmHandle</i> specifies is closed.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>CreateOptions </i>parameter's value is invalid or the <i>Description</i> parameter's string is too long.
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>The <i>CreateOptions </i>parameter does not specify RESOURCE_MANAGER_VOLATILE but the transaction manager that <i>TmHandle</i> specifies is volatile.
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>The GUID that <i>ResourceManagerGuid </i>specifies already exists.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The value of the <i>DesiredAccess</i> parameter is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## -remarks
A resource manager that calls <b>ZwCreateResourceManager</b> must eventually call <a href="kernel.zwclose">ZwClose</a> to close the object handle.

For more information about <b>ZwCreateResourceManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwcreateenlistment">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="kernel.zwcreatetransactionmanager">ZwCreateTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwgetnotificationresourcemanager">ZwGetNotificationResourceManager</a>
</dt>
<dt>
<a href="kernel.zwopenresourcemanager">ZwOpenResourceManager</a>
</dt>
<dt>
<a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationresourcemanager">ZwQueryInformationResourceManager</a>
</dt>
<dt>
<a href="kernel.zwrecoverresourcemanager">ZwRecoverResourceManager</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateResourceManager routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
