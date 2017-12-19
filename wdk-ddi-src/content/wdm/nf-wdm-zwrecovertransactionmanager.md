---
UID: NF.wdm.ZwRecoverTransactionManager
title: ZwRecoverTransactionManager function
author: windows-driver-content
description: The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.
old-location: kernel\zwrecovertransactionmanager.htm
old-project: kernel
ms.assetid: 20284cad-5d65-4d22-98fa-6b6c5f6b422d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwRecoverTransactionManager
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
req.alt-api: ZwRecoverTransactionManager,NtRecoverTransactionManager
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

# ZwRecoverTransactionManager function



## -description
The <b>ZwRecoverTransactionManager</b> routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.



## -syntax

````
NTSTATUS ZwRecoverTransactionManager(
  _In_ HANDLE TransactionManagerHandle
);
````


## -parameters

### -param TransactionManagerHandle [in]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> that was obtained by a previous call to <a href="kernel.zwcreatetransactionmanager">ZwCreateTransactionManager</a> or <a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>. The handle must have TRANSACTIONMANAGER_RECOVER access to the object.


## -returns
<b>ZwRecoverTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The specified handle is not a handle to a transaction manager object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the transaction manager object.
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>The transaction manager object is volatile and, therefore, its transactions cannot be recovered.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The transaction manager object is not in a state that allows recovery.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The <b>ZwRecoverTransactionManager</b> routine tries to reconstruct the state of the transaction manager object, including all transactions, enlistments, and resource managers, from the recovery information that is in the object's log stream, beginning at the last <a href="https://msdn.microsoft.com/310545f6-d10d-481e-829d-287b045b98cd">restart area</a> that KTM created and ending at the stream's end.

To recover up to a specific virtual time, use the <a href="kernel.zwrollforwardtransactionmanager">ZwRollforwardTransactionManager</a> routine instead of <b>ZwRecoverTransactionManager</b>.

Your TPS component must call <b>ZwRecoverTransactionManager</b> after it has called <a href="kernel.zwcreatetransactionmanager">ZwCreateTransactionManager</a> or <a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>.

For more information about recovery operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

<b>NtRecoverTransactionManager</b> and <b>ZwRecoverTransactionManager</b> are two versions of the same Windows Native System Services routine.

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
<a href="kernel.tmrecovertransactionmanager">TmRecoverTransactionManager</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwcreatetransactionmanager">ZwCreateTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwopentransactionmanager">ZwOpenTransactionManager</a>
</dt>
<dt>
<a href="kernel.zwrollforwardtransactionmanager">ZwRollforwardTransactionManager</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwRecoverTransactionManager routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

