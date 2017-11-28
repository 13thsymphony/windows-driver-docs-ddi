---
UID: NF.wdm.NtRollbackTransaction
title: NtRollbackTransaction
author: windows-driver-content
description: The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction.
old-location: kernel\zwrollbacktransaction.htm
old-project: kernel
ms.assetid: 865349bd-400d-4acf-a2f7-33da128702be
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: NtRollbackTransaction
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
req.alt-api: ZwRollbackTransaction,NtRollbackTransaction
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
req.iface: 
req.product: Windows 10 or later.
---

# NtRollbackTransaction function



## -description
<p>The <b>ZwRollbackTransaction</b> routine initiates a rollback operation for a specified transaction.</p>


## -syntax

````
NTSTATUS ZwRollbackTransaction(
  _In_ HANDLE  TransactionHandle,
  _In_ BOOLEAN Wait
);
````


## -parameters
<dl>

### -param <i>TransactionHandle</i> [in]

<dd>
<p>A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a> that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>. The handle must have TRANSACTION_ROLLBACK access to the object.</p>
</dd>

### -param <i>Wait</i> [in]

<dd>
<p>A Boolean value that the caller sets to <b>TRUE</b> for synchronous operation or <b>FALSE</b> for asynchronous operation. If this parameter is set to <b>TRUE</b>, the call does not return until the rollback operation is complete.</p>
</dd>
</dl>

## -returns
<p><b>ZwRollbackTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:</p><dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><p>The handle that the <i>TransactionHandle</i> parameter specifies is not a handle to a transaction object.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p>An object handle is invalid.</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The caller does not have appropriate access to the transaction object.</p><dl>
<dt><b>STATUS_TRANSACTION_ALREADY_COMMITTED</b></dt>
</dl><p>The transaction cannot be rolled back because it has already been committed.</p><dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl><p>The transaction has not been committed but its current state does not permit rollback.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p>Rollback notifications have been queued to resource managers, and the caller specified <b>FALSE</b> for the <i>Wait</i> parameter.</p>

<p> </p>

<p>The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

## -remarks
<p>For more information about <b>ZwRollbackTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546928">Handling Rollback Operations</a>.</p>

<p><b>NtRollbackEnlistment</b> and <b>ZwRollbackEnlistment</b> are two versions of the same Windows Native System Services routine.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

<p>For more information about <b>ZwRollbackTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546928">Handling Rollback Operations</a>.</p>

<p><b>NtRollbackEnlistment</b> and <b>ZwRollbackEnlistment</b> are two versions of the same Windows Native System Services routine.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later operating system versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566420">ZwCommitTransaction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwRollbackTransaction routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
