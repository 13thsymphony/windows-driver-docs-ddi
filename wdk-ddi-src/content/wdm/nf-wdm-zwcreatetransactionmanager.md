---
UID: NF.wdm.ZwCreateTransactionManager
title: ZwCreateTransactionManager function
author: windows-driver-content
description: The ZwCreateTransactionManager routine creates a new transaction manager object.
old-location: kernel\zwcreatetransactionmanager.htm
old-project: kernel
ms.assetid: 9c9f0a8b-7add-4ab1-835d-39f508ce32a9
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ZwCreateTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwCreateTransactionManager,NtCreateTransactionManager
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

# ZwCreateTransactionManager function



## -description
The <b>ZwCreateTransactionManager</b> routine creates a new transaction manager object.



## -syntax

````
NTSTATUS ZwCreateTransactionManager(
  _Out_    PHANDLE            TmHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ PUNICODE_STRING    LogFileName,
  _In_opt_ ULONG              CreateOptions,
  _In_opt_ ULONG              CommitStrength
);
````


## -parameters

### -param TmHandle [out]

A pointer to a caller-allocated variable that receives a handle to the new <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction manager object. In addition to the access rights that are defined for all kinds of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify any of the following access right flags for transaction manager objects. 

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Allows the caller to</th>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_CREATE_RM

</td>
<td>
Create a resource manager (see <a href="kernel.zwcreateresourcemanager">ZwCreateResourceManager</a>).

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_QUERY_INFORMATION

</td>
<td>
Obtain information about the transaction manager (see <a href="kernel.zwqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> and <a href="kernel.zwenumeratetransactionobject">ZwEnumerateTransactionObject</a>). Also required for <a href="kernel.zwopenresourcemanager">ZwOpenResourceManager</a>, <a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>, and <a href="kernel.zwopentransaction">ZwOpenTransaction</a>.) 

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_RECOVER

</td>
<td>
Recover the transaction manager (see <a href="kernel.zwrecovertransactionmanager">ZwRecoverTransactionManager</a> and <a href="kernel.zwrollforwardtransactionmanager">ZwRollforwardTransactionManager</a>).

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_RENAME

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_SET_INFORMATION

</td>
<td>
Not used.

</td>
</tr>
</table>
 

Alternatively, you can specify one or more of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmaps. These bitmaps combine the flags from the previous table with the STANDARD_RIGHTS_<i>XXX</i> flags that are described on the <b>ACCESS_MASK</b> reference page. You can also combine these bitmaps with additional flags from the preceding table. The following table shows how the bitmaps correspond to specific access rights.

<table>
<tr>
<th>Rights bitmap</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ and TRANSACTIONMANAGER_QUERY_INFORMATION

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, TRANSACTIONMANAGER_SET_INFORMATION, TRANSACTIONMANAGER_RECOVER, TRANSACTIONMANAGER_RENAME, and TRANSACTIONMANAGER_CREATE_RM

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE

</td>
</tr>
<tr>
<td>
TRANSACTIONMANAGER_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_REQUIRED, TRANSACTIONMANAGER_GENERIC_READ, TRANSACTIONMANAGER_GENERIC_WRITE, and TRANSACTIONMANAGER_GENERIC_EXECUTE 

</td>
</tr>
</table>
 


### -param ObjectAttributes [in, optional]

A pointer to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.


### -param LogFileName [in, optional]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains the path and file name of a <a href="https://msdn.microsoft.com/d7ad0e16-d1f2-4c41-b647-95b5445c2708">CLFS log file stream</a> to be associated with the transaction manager object. This parameter must be <b>NULL</b> if the <i>CreateOptions</i> parameter is TRANSACTION_MANAGER_VOLATILE. Otherwise, this parameter must be non-<b>NULL</b>. For more information, see the following Remarks section.


### -param CreateOptions [in, optional]

Optional object creation flags. The following table contains the available flags, which are defined in Ktmtypes.h.

<table>
<tr>
<th>Option flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_VOLATILE

</td>
<td>
The transaction manager object will be volatile. Therefore, it will not use a log file.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_DEFAULT

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_VOLUME

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_HIVES

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_LOWEST

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_RECOVERY

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_PROGRESS

</td>
<td>
For internal use only.

</td>
</tr>
</table>
 


### -param CommitStrength [in, optional]

Reserved for future use. This parameter must be zero. 


## -returns
<b>ZwCreateTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The value of an input parameter is invalid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>KTM could not allocate system resources (typically memory).
<dl>
<dt><b>STATUS_LOG_CORRUPTION_DETECTED</b></dt>
</dl>KTM encountered an error while creating or opening the log file.
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>A security descriptor contains an invalid access control list (ACL).
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>A security descriptor contains an invalid security identifier (SID).
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>The object name that the <i>ObjectAttributes </i>parameter specifies already exists.
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>The operating system detected a duplicate object name. The error might indicate that the log stream is already being used.
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>The object name that the <i>ObjectAttributes </i>parameter specifies is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The value of the <i>DesiredAccess</i> parameter is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
If the log file stream that the <i>LogFileName </i>parameter specifies does not exist, KTM calls CLFS to create the stream. If the stream already exists, KTM calls CLFS to open the stream.

Your TPS component must call <a href="kernel.zwrecovertransactionmanager">ZwRecoverTransactionManager</a> after it has called <b>ZwCreateTransactionManager</b>

If your TPS component specifies the TRANSACTION_MANAGER_VOLATILE flag in the <i>CreateOptions </i>parameter, all resource managers that are associated with the transaction manager object must specify the RESOURCE_MANAGER_VOLATILE flag when they call <a href="kernel.zwcreateresourcemanager">ZwCreateResourceManager</a>.

A TPS component that calls <b>ZwCreateTransactionManager</b> must eventually call <a href="kernel.zwclose">ZwClose</a> to close the object handle.

For more information about how use <b>ZwCreateTransactionManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

<b>NtCreateTransactionManager</b> and <b>ZwCreateTransactionManager</b> are two versions of the same Windows Native System Services routine. 

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
<dt>Wdm.h (include Wdm.h or Ntifs.h)</dt>
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
<a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwrecovertransactionmanager">ZwRecoverTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwrollforwardtransactionmanager">ZwRollforwardTransactionManager</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateTransactionManager routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

