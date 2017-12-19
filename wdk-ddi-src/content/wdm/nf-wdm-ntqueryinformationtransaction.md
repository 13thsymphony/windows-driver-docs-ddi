---
UID: NF.wdm.NtQueryInformationTransaction
title: NtQueryInformationTransaction function
author: windows-driver-content
description: The ZwQueryInformationTransaction routine retrieves information about a specified transaction.
old-location: kernel\zwqueryinformationtransaction.htm
old-project: kernel
ms.assetid: b4a4cc4b-8f23-4dd6-81d3-4cb2c861ba4f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: NtQueryInformationTransaction
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
req.alt-api: ZwQueryInformationTransaction,NtQueryInformationTransaction
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

# NtQueryInformationTransaction function



## -description
The <b>ZwQueryInformationTransaction</b> routine retrieves information about a specified transaction.



## -syntax

````
NTSTATUS ZwQueryInformationTransaction(
  _In_      HANDLE                        TransactionHandle,
  _In_      TRANSACTION_INFORMATION_CLASS TransactionInformationClass,
  _Out_     PVOID                         TransactionInformation,
  _In_      ULONG                         TransactionInformationLength,
  _Out_opt_ PULONG                        ReturnLength
);
````


## -parameters

### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="kernel.zwcreatetransaction">ZwCreateTransaction</a> or <a href="kernel.zwopentransaction">ZwOpenTransaction</a>. The handle must have TRANSACTION_QUERY_INFORMATION access to the object.


### -param TransactionInformationClass [in]

A <a href="kernel.transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>-typed value that specifies the information to obtain. The value must be one of the following values:

<ul>
<li>
<b>TransactionBasicInformation</b>

</li>
<li>
<b>TransactionPropertiesInformation</b>

</li>
<li>
<b>TransactionEnlistmentInformation</b>

</li>
</ul>
The <b>TransactionFullInformation</b> value is not used with <b>ZwQueryInformationTransaction</b>.


### -param TransactionInformation [out]

A pointer to a caller-allocated buffer that receives the information that the <i>TransactionInformationClass</i> parameter specifies. The buffer's structure type must be <a href="kernel.transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>, <a href="kernel.transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>, or <a href="kernel.transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a>.


### -param TransactionInformationLength [in]

The length, in bytes, of the buffer that the <i>TransactionInformation</i> parameter points to, including the length of any additional array elements that the caller has allocated to receive information.


### -param ReturnLength [out, optional]

A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>TransactionInformation</i> buffer. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>ZwQueryInformationTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>The <i>TransactionInformationClass</i> parameter's value is invalid.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The length of the buffer that is specified by the <i>TransactionInformationLength</i> parameter is incorrect.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The handle that the <i>TransactionHandle </i>parameter specifies is not a handle to a transaction object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the transaction object.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer that the <i>TransactionInformation </i>parameter specifies is too small.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
For more information about how to use <b>ZwQueryInformationTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542876">Creating a Transactional Client</a>.

<b>NtQueryInformationTransaction</b> and <b>ZwQueryInformationTransaction</b> are two versions of the same Windows Native System Services routine.

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
<a href="kernel.tmgettransactionid">TmGetTransactionId</a>
</dt>
<dt>
<a href="kernel.transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="kernel.transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a>
</dt>
<dt>
<a href="kernel.transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>
</dt>
<dt>
<a href="kernel.zwopentransaction">ZwOpenTransaction</a>
</dt>
<dt>
<a href="kernel.zwsetinformationtransaction">ZwSetInformationTransaction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryInformationTransaction routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

