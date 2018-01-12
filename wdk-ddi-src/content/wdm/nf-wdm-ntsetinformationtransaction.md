---
UID: NF:wdm.NtSetInformationTransaction
title: NtSetInformationTransaction function
author: windows-driver-content
description: The ZwSetInformationTransaction routine sets information for a specified transaction.
old-location: kernel\zwsetinformationtransaction.htm
old-project: kernel
ms.assetid: 47e729d8-241e-47f0-a595-d95c5ac516a4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: NtSetInformationTransaction
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
req.alt-api: ZwSetInformationTransaction,NtSetInformationTransaction
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

# NtSetInformationTransaction function



## -description
The <b>ZwSetInformationTransaction</b> routine sets information for a specified transaction.



## -syntax

````
NTSTATUS ZwSetInformationTransaction(
  _In_ HANDLE                        TransactionHandle,
  _In_ TRANSACTION_INFORMATION_CLASS TransactionInformationClass,
  _In_ PVOID                         TransactionInformation,
  _In_ ULONG                         TransactionInformationLength
);
````


## -parameters

### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>. The handle must have TRANSACTION_SET_INFORMATION access to the object.


### -param TransactionInformationClass [in]

A <a href="..\wdm\ne-wdm-_transaction_information_class.md">TRANSACTION_INFORMATION_CLASS</a>-typed value that specifies the type of information to set. The value must be <b>TransactionPropertiesInformation</b>.


### -param TransactionInformation [in]

A pointer to a caller-allocated buffer that contains the information to set. The buffer's structure type must be <a href="..\wdm\ns-wdm-_transaction_properties_information.md">TRANSACTION_PROPERTIES_INFORMATION</a>.


### -param TransactionInformationLength [in]

The length, in bytes, of the buffer that the <i>TransactionInformation</i> parameter points to.


## -returns
<b>ZwSetInformationTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>The <i>TransactionInformationClass </i>parameter's value is invalid.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The handle that the <i>TransactionHandle</i> parameter specifies is not a handle to a transaction object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the transaction object.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <i>TransactionInformationLength </i>parameter's value is invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The contents of the buffer that the <i>TransactionInformation </i>buffer specifies is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
For more information about <b>ZwSetInformationTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542876">Creating a Transactional Client</a>.

<b>NtSetInformationTransaction</b> and <b>ZwSetInformationTransaction</b> are two versions of the same Windows Native System Services routine.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm-_transaction_information_class.md">TRANSACTION_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_transaction_properties_information.md">TRANSACTION_PROPERTIES_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationTransaction routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

