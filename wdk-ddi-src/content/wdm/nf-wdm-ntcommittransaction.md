---
UID: NF:wdm.NtCommitTransaction
title: NtCommitTransaction function
author: windows-driver-content
description: The ZwCommitTransaction routine initiates a commit operation for a specified transaction.
old-location: kernel\zwcommittransaction.htm
old-project: kernel
ms.assetid: 145646f3-ff90-41d6-bf76-947cdf93b489
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: NtCommitTransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwCommitTransaction,NtCommitTransaction
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

# NtCommitTransaction function



## -description
The <b>ZwCommitTransaction</b> routine initiates a commit operation for a specified transaction.



## -syntax

````
NTSTATUS ZwCommitTransaction(
  _In_ HANDLE  TransactionHandle,
  _In_ BOOLEAN Wait
);
````


## -parameters

### -param TransactionHandle [in]

A handle to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. Your component receives this handle from <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>. The handle must have TRANSACTION_COMMIT access to the object.


### -param Wait [in]

A Boolean value that the caller sets to <b>TRUE</b> for synchronous operation or <b>FALSE</b> for asynchronous operation. If this parameter is <b>TRUE</b>, the call returns after the commit operation is complete.


## -returns
<b>ZwCommitTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The handle that was specified for the <i>TransactionHandle</i> parameter is not a handle to a transaction object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The specified transaction object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
        The caller does not have appropriate access to the transaction object.
       
<dl>
<dt><b>STATUS_TRANSACTION_SUPERIOR_EXISTS</b></dt>
</dl>The caller cannot commit the transaction because a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> exists.
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_ABORTED</b></dt>
</dl>The transaction cannot be committed because it has been rolled back.
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_COMMITTED</b></dt>
</dl>The transaction is already committed.
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>The commit operation for this transaction has already been started.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>Commit notifications have been queued to resource managers, and the caller specified <b>FALSE</b> for the <i>Wait</i> parameter.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
For more information about how transaction clients should use the <b>ZwCommitTransaction</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542876">Creating a Transactional Client</a>.

For more information about commit operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546783">Handling Commit Operations</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-tmcommittransaction.md">TmCommitTransaction</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCommitTransaction routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

