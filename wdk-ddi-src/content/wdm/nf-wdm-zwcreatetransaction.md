---
UID: NF:wdm.ZwCreateTransaction
title: ZwCreateTransaction function
author: windows-driver-content
description: The ZwCreateTransaction routine creates a transaction object.
old-location: kernel\zwcreatetransaction.htm
old-project: kernel
ms.assetid: b4c2dd68-3c1a-46d3-ab9c-be2291ed80f4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwCreateTransaction
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
req.alt-api: ZwCreateTransaction,NtCreateTransaction
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwCreateTransaction function



## -description
The <b>ZwCreateTransaction</b> routine creates a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.



## -syntax

````
NTSTATUS ZwCreateTransaction(
  _Out_    PHANDLE            TransactionHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ LPGUID             Uow,
  _In_opt_ HANDLE             TmHandle,
  _In_opt_ ULONG              CreateOptions,
  _In_opt_ ULONG              IsolationLevel,
  _In_opt_ ULONG              IsolationFlags,
  _In_opt_ PLARGE_INTEGER     Timeout,
  _In_opt_ PUNICODE_STRING    Description
);
````


## -parameters

### -param TransactionHandle [out]

A pointer to a caller-allocated variable that receives a handle to the new transaction object, if the call to <b>ZwCreateTransaction</b> succeeds.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction object. In addition to the access rights that are defined for all kinds of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify any of the following flags for transaction objects.

<table>
<tr>
<th>Access mask</th>
<th>Allows the caller to</th>
</tr>
<tr>
<td>
TRANSACTION_COMMIT

</td>
<td>
Commit the transaction (see <a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a>).

</td>
</tr>
<tr>
<td>
TRANSACTION_ENLIST

</td>
<td>
Create an enlistment for the transaction (see <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>).

</td>
</tr>
<tr>
<td>
TRANSACTION_PROPAGATE

</td>
<td>
Do not use. 

</td>
</tr>
<tr>
<td>
TRANSACTION_QUERY_INFORMATION

</td>
<td>
Obtain information about the transaction (see <a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>).

</td>
</tr>
<tr>
<td>
TRANSACTION_ROLLBACK

</td>
<td>
Roll back the transaction (see <a href="..\wdm\nf-wdm-zwrollbacktransaction.md">ZwRollbackTransaction</a>).

</td>
</tr>
<tr>
<td>
TRANSACTION_SET_INFORMATION

</td>
<td>
Set information for the transaction (see <a href="..\wdm\nf-wdm-zwsetinformationtransaction.md">ZwSetInformationTransaction</a>).

</td>
</tr>
</table>
 

Alternatively, you can specify one or more of the following ACCESS_MASK bitmaps. These bitmaps combine the flags from the previous table with the STANDARD_RIGHTS_<i>XXX</i> flags that are described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> reference page. You can also combine these bitmaps with additional flags from the preceding table. The following table shows how the bitmaps correspond to specific access rights.

<table>
<tr>
<th>Rights bitmap</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
TRANSACTION_GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, TRANSACTION_QUERY_INFORMATION, and SYNCHRONIZE

</td>
</tr>
<tr>
<td>
TRANSACTION_GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, TRANSACTION_SET_INFORMATION, TRANSACTION_COMMIT, TRANSACTION_ENLIST, TRANSACTION_ROLLBACK, TRANSACTION_PROPAGATE, TRANSACTION_SAVEPOINT, and SYNCHRONIZE

</td>
</tr>
<tr>
<td>
TRANSACTION_GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, TRANSACTION_COMMIT, TRANSACTION_ROLLBACK, and SYNCHRONIZE

</td>
</tr>
<tr>
<td>
TRANSACTION_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_REQUIRED, TRANSACTION_GENERIC_READ, TRANSACTION_GENERIC_WRITE, and TRANSACTION_GENERIC_EXECUTE

</td>
</tr>
<tr>
<td>
TRANSACTION_RESOURCE_MANAGER_RIGHTS

</td>
<td>
STANDARD_RIGHTS_WRITE, TRANSACTION_GENERIC_READ, TRANSACTION_SET_INFORMATION, TRANSACTION_ENLIST, TRANSACTION_ROLLBACK, TRANSACTION_PROPAGATE, and SYNCHRONIZE

</td>
</tr>
</table>
 

Typically, a resource manager specifies TRANSACTION_RESOURCE_MANAGER_RIGHTS.

The <i>DesiredAccess</i> value cannot be zero.


### -param ObjectAttributes [in, optional]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.


### -param Uow [in, optional]

A pointer to a GUID that KTM uses as the new transaction object's <a href="https://msdn.microsoft.com/927a417b-35f5-49b8-85f3-7e6b1f5c0225">unit of work (UOW) identifier</a>. This parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, KTM generates a GUID and assigns it to the transaction object. For more information, see the following Remarks section.


### -param TmHandle [in, optional]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a> or <a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>. KTM assigns the new transaction object to the specified transaction manager object. If this parameter is <b>NULL</b>, KTM assigns the new transaction object to a transaction manager later, when a resource manager creates an enlistment for the transaction. 


### -param CreateOptions [in, optional]

Optional object creation flags. The following table contains the available flags, which are defined in Ktmtypes.h.

<table>
<tr>
<th>Option flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_DO_NOT_PROMOTE

</td>
<td>
Reserved for future use.

</td>
</tr>
</table>
 


### -param IsolationLevel [in, optional]

Reserved for future use. Callers must set this parameter to zero.


### -param IsolationFlags [in, optional]

Reserved for future use. Callers should set this parameter to zero.


### -param Timeout [in, optional]

A pointer to a time-out value. If the transaction has not been committed by the time specified by this parameter, KTM rolls back the transaction. The time-out value is expressed in system time units (100-nanosecond intervals), and can specify either an absolute time or a relative time. If the value pointed to by <i>Timeout</i> is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. This pointer is optional and can be <b>NULL</b> if you do not want the transaction to have a time-out value. If <i>Timeout</i> = <b>NULL</b> or *<i>Timeout</i> = 0, the transaction never times out. (You can also use <a href="..\wdm\nf-wdm-zwsetinformationtransaction.md">ZwSetInformationTransaction</a> to set a time-out value.)


### -param Description [in, optional]

A pointer to a caller-supplied <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a NULL-terminated string. The string provides a description of the transaction. KTM stores a copy of the string and includes the string in messages that it writes to the log stream. The maximum string length is MAX_TRANSACTION_DESCRIPTION_LENGTH. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>ZwCreateTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>CreateOptions</i> parameter contains an invalid flag, the <i>DesiredAccess</i> parameter is zero, or the <i>Description</i> parameter's string is too long.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>KTM could not allocate system resources (typically memory).
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>A security descriptor contains an invalid access control list (ACL).
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>A security descriptor contains an invalid security identifier (SID).
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>The object name that the <i>ObjectAttributes</i> parameter specifies already exists.
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>The object name that the <i>ObjectAttributes</i> parameter specifies is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The value of the <i>DesiredAccess</i> parameter is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The caller can use the <i>Uow</i> parameter to specify a UOW identifier for the transaction object. If the caller does not specify a UOW identifier, KTM generates a GUID and assigns it to the transaction object. The caller can later obtain this GUID by calling <a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>.

Typically, you should let KTM generate a GUID for the transaction object, unless your component communicates with another TPS component that has already generated a UOW identifier for the transaction.

To close the transaction handle, the component that called <b>ZwCreateTransaction</b> must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. If the last transaction handle closes before any component calls <a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a> for the transaction, KTM rolls back the transaction.

For more information about how transaction clients should use <b>ZwCreateTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542876">Creating a Transactional Client</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcommittransaction.md">ZwCommitTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwrollbacktransaction.md">ZwRollbackTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetinformationtransaction.md">ZwSetInformationTransaction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateTransaction routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

