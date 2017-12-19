---
UID: NF.wdm.ZwCreateKeyTransacted
title: ZwCreateKeyTransacted function
author: windows-driver-content
description: The ZwCreateKeyTransacted routine creates a new registry key or opens an existing one, and it associates the key with a transaction.
old-location: kernel\zwcreatekeytransacted.htm
old-project: kernel
ms.assetid: c0cf38f4-2820-4177-93e6-2e20524d0353
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwCreateKeyTransacted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwCreateKeyTransacted
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

# ZwCreateKeyTransacted function



## -description
The <b>ZwCreateKeyTransacted</b> routine creates a new registry key or opens an existing one, and it associates the key with a transaction. 



## -syntax

````
NTSTATUS ZwCreateKeyTransacted(
  _Out_      PHANDLE            KeyHandle,
  _In_       ACCESS_MASK        DesiredAccess,
  _In_       POBJECT_ATTRIBUTES ObjectAttributes,
  _Reserved_ ULONG              TitleIndex,
  _In_opt_   PUNICODE_STRING    Class,
  _In_       ULONG              CreateOptions,
  _In_       HANDLE             TransactionHandle,
  _Out_opt_  PULONG             Disposition
);
````


## -parameters

### -param KeyHandle [out]

A pointer to a HANDLE variable into which the routine writes the handle to the key. 


### -param DesiredAccess [in]

Specifies the type of access to the key that the caller requests. This parameter is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value. For more information, see the description of the <i>DesiredAccess</i> parameter of the <a href="kernel.zwcreatekey">ZwCreateKey</a> routine. 


### -param ObjectAttributes [in]

A pointer to the object attributes of the key being opened. This parameter points to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that must have been previously initialized by the <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a> routine. The caller must specify the name of the registry key as the <i>ObjectName</i> parameter in the call to <b>InitializeObjectAttributes</b>. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param TitleIndex 

Device and intermediate drivers set this parameter to zero. 


### -param Class [in, optional]

Device and intermediate drivers set this parameter to <b>NULL</b>. 


### -param CreateOptions [in]

Specifies the options to apply when the routine creates or opens the key. Set this parameter to zero or to the bitwise OR of one or more of the following REG_OPTION_<i>XXX</i> flag bits.

<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_VOLATILE

</td>
<td>
The key is <u>not</u> preserved after the computer restarts.

</td>
</tr>
<tr>
<td>
REG_OPTION_NON_VOLATILE

</td>
<td>
The key is preserved after the computer restarts.

</td>
</tr>
<tr>
<td>
REG_OPTION_CREATE_LINK

</td>
<td>
The key is a symbolic link. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE

</td>
<td>
Open the key with special privileges that enable backup and restore operations. This flag is not used by device and intermediate drivers.

</td>
</tr>
</table>
 


### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this handle, you can call the <a href="kernel.zwcreatetransaction">ZwCreateTransaction</a> routine. Or, if you have a pointer to a transaction object, you can supply the pointer to the <a href="ifsk.obopenobjectbypointer">ObOpenObjectByPointer</a> routine to obtain the corresponding transaction handle.


### -param Disposition [out, optional]

A pointer to a location into which the routine writes one of the following values to indicate whether the call created a new key or opened an existing one.

<table>
<tr>
<th><i>Disposition</i> value</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_CREATED_NEW_KEY

</td>
<td>
A new key was created.

</td>
</tr>
<tr>
<td>
REG_OPENED_EXISTING_KEY

</td>
<td>
An existing key was opened.

</td>
</tr>
</table>
 

You can set <i>Disposition</i> = <b>NULL</b> if this information is not needed.


## -returns
<b>ZwCreateKeyTransacted</b> returns STATUS_SUCCESS if the call successfully creates or opens the key. Possible error return values include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl> The <i>ObjectAttributes</i> parameter is <b>NULL</b> or points to invalid information, or the <i>CreateOptions</i> parameter value specifies invalid options.
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>The registry path in the object attributes is invalid.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The registry path in the object attributes was not found.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required access rights to open a handle for the named registry key.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory allocation operation failed.

 


## -remarks
This routine provides a handle that the caller can access a registry key with. Additionally, this routine associates the key with an active transaction.

After the handle that is pointed to by <i>KeyHandle</i> is no longer being used, the driver must call the <a href="kernel.zwclose">ZwClose</a> routine to close it.

Like <b>ZwCreateKeyTransacted</b>, the <a href="kernel.zwopenkeytransacted">ZwOpenKeyTransacted</a> routine associates a key with a transaction. Unlike <b>ZwCreateKeyTransacted</b>, which can create a new key or open an existing key, <b>ZwOpenKeyTransacted</b> can only open a registry key that already exists.

After a kernel-mode driver obtains a handle to a transaction (for example, by calling <b>ZwCreateTransaction</b>), the driver can perform a series of registry operations that are part of this transaction. The driver can close the transaction either by committing to the changes that were made in the transaction or by rolling back the transaction.

After the driver successfully completes all registry operations that are part of a transaction, it can call the <a href="kernel.zwcommittransaction">ZwCommitTransaction</a> routine to commit to the changes. The driver can call the <a href="kernel.zwrollbacktransaction">ZwRollbackTransaction</a> routine to roll back the transaction.

During a transaction, a registry operation is part of the transaction if the system call that performs the operation meets either of the following conditions:

The call specifies, as an input parameter, the transaction handle. For example, calls to <b>ZwCreateKeyTransacted</b> and <b>ZwOpenKeyTransacted</b> can associate one or more handles to registry keys with the transaction. 

The call specifies, as an input parameter, a registry key handle that was obtained by a call to <b>ZwCreateKeyTransacted</b> or <b>ZwOpenKeyTransacted</b> to which the transaction handle was supplied. For example, a call to the <a href="kernel.zwsetvaluekey">ZwSetValueKey</a> routine can use a key handle that was obtained in this way to set the value of a registry key as part of a transaction. 

For more information about kernel-mode transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565408">Using Kernel Transaction Manager</a>.

The security descriptor in the object attributes determines whether the access rights that are specified by the <i>DesiredAccess</i> parameter are granted on later calls to routines, such as <b>ZwOpenKeyTransacted</b> that access the key, or to routines, such as <b>ZwCreateKeyTransacted,</b> that create subkeys of the key.

If the kernel-mode caller is not running in a system thread context, it must ensure that any handles it creates are kernel handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about how to work with registry keys in kernel mode, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>. 


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
Available in Windows Vista and later versions of Windows. 

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
<a href="ifsk.obopenobjectbypointer">ObOpenObjectByPointer</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwcommittransaction">ZwCommitTransaction</a>
</dt>
<dt>
<a href="kernel.zwcreatekey">ZwCreateKey</a>
</dt>
<dt>
<a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>
</dt>
<dt>
<a href="kernel.zwopenkeytransacted">ZwOpenKeyTransacted</a>
</dt>
<dt>
<a href="kernel.zwrollbacktransaction">ZwRollbackTransaction</a>
</dt>
<dt>
<a href="kernel.zwsetvaluekey">ZwSetValueKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateKeyTransacted routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

