---
UID: NF:fltkernel.FltCommitFinalizeComplete
title: FltCommitFinalizeComplete function
author: windows-driver-content
description: The FltCommitFinalizeComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification.
old-location: ifsk\fltcommitfinalizecomplete.htm
old-project: ifsk
ms.assetid: e1bfef9f-87c8-49e0-bbc4-6bc5ea103758
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltcommitfinalizecomplete, FltCommitFinalizeComplete, fltkernel/FltCommitFinalizeComplete, FltCommitFinalizeComplete routine [Installable File System Drivers], FltApiRef_a_to_d_f2b874db-f5fb-405b-a3a5-b5877c88548d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista Service Pack 1 (SP1) and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fltmgr.lib
-	Fltmgr.dll
apiname:
-	FltCommitFinalizeComplete
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltCommitFinalizeComplete function
The <b>FltCommitFinalizeComplete</b> routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification.

## Syntax

````
NTSTATUS FltCommitFinalizeComplete(
  _In_     PFLT_INSTANCE Instance,
  _In_     PKTRANSACTION Transaction,
  _In_opt_ PFLT_CONTEXT  TransactionContext
);
````

## Parameters

`Instance`

Opaque pointer to an instance of a minifilter driver. This parameter is required and cannot be <b>NULL</b>.

`Transaction`

Opaque pointer to the transaction the minifilter driver is currently enlisted in. This parameter is required and cannot be <b>NULL</b>.

`TransactionContext`

Pointer to the minifilter driver's context for the transaction. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>FltCommitFinalizeComplete</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver did not set a context on the transaction. This is an error code. 

</td>
</tr>
</table>

## Remarks

A minifilter driver that is enlisted in a transaction can receive a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification when the transaction is fully committed (that is, when all of the <a href="http://go.microsoft.com/fwlink/p/?linkid=94490">resource managers</a> associated with the transaction, such as <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed). For an antivirus minifilter driver that performs scans outside of transactions, you can use this notification value to determine when the driver should begin scanning files.

To send the TRANSACTION_NOTIFY_COMMIT_FINALIZE notification to the minifilter driver, the filter manager calls the minifilter driver's <i>TransactionNotificationCallback</i> routine. The minifilter driver acknowledges this notification in one of two ways:
<ul>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine performs any required processing and returns STATUS_SUCCESS. (In this case, the minifilter driver does not call <b>FltCommitFinalizeComplete</b>.)

</li>
<li>
The minifilter driver's <i>TransactionNotificationCallback</i> routine posts any required processing to a worker thread and returns STATUS_PENDING. After performing the processing asynchronously, the minifilter driver's worker thread routine must call <b>FltCommitFinalizeComplete</b> to indicate that it has finished this processing. If the minifilter driver's worker thread routine does not call <b>FltCommitFinalizeComplete</b>, certain system resources will be leaked.

</li>
</ul>To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 

To enlist in a transaction, call <a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>.

To allocate a new transaction context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To set a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">Transaction Notifications</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista Service Pack 1 (SP1) and later. Available in Windows Vista Service Pack 1 (SP1) and later. |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | Fltmgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>

<a href="..\fltkernel\nf-fltkernel-fltrollbackenlistment.md">FltRollbackEnlistment</a>

<a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>

<a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>

<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>

<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>

<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>

<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>

<a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>

<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>

<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCommitFinalizeComplete routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>