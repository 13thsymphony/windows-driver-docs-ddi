---
UID: NF.fltkernel.FltEnlistInTransaction
title: FltEnlistInTransaction function
author: windows-driver-content
description: The FltEnlistInTransaction routine enlists a minifilter driver in a given transaction.
old-location: ifsk\fltenlistintransaction.htm
old-project: ifsk
ms.assetid: c4b82596-824f-488e-96cd-17bd850494e5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltEnlistInTransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltEnlistInTransaction
req.alt-loc: FltMgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: <= APC_LEVEL
---

# FltEnlistInTransaction function



## -description
The <b>FltEnlistInTransaction</b> routine enlists a minifilter driver in a given transaction. 


## -syntax

````
NTSTATUS FltEnlistInTransaction(
  _In_ PFLT_INSTANCE     Instance,
  _In_ PKTRANSACTION     Transaction,
  _In_ PFLT_CONTEXT      TransactionContext,
  _In_ NOTIFICATION_MASK NotificationMask
);
````


## -parameters

### -param Instance [in]

An opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 

### -param Transaction [in]

An opaque transaction pointer for the transaction. 

### -param TransactionContext [in]

A pointer to the minifilter driver's transaction context. This parameter is required and cannot be <b>NULL</b>. 

### -param NotificationMask [in]

Specifies the type of notifications that the filter manager is to send to the minifilter driver, as one or more of the values listed in the following table. This parameter is required and cannot be zero. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_COMMIT
</td>
<td>
This notification is sent when the transaction is being committed. 
</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_COMMIT_FINALIZE
</td>
<td>
For Windows Vista SP1 and later, this notification is sent when the transaction is fully committed (that is, when all of the <a href="http://go.microsoft.com/fwlink/p/?linkid=94490">resource managers</a> associated with the transaction, such as <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">TxF</a>, have committed).
</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPARE
</td>
<td>
This notification is sent when the transaction has entered the prepare for commit phase. 
</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_PREPREPARE
</td>
<td>
This notification is sent when the transaction has entered the pre-prepare for commit phase. 
</td>
</tr>
<tr>
<td>
TRANSACTION_NOTIFY_ROLLBACK
</td>
<td>
This notification is sent when the transaction is being rolled back or aborted. 
</td>
</tr>
<tr>
<td>
FLT_MAX_TRANSACTION_NOTIFICATIONS
</td>
<td>
TRANSACTION_NOTIFY_COMMIT | TRANSACTION_NOTIFY_PREPARE | TRANSACTION_NOTIFY_PREPREPARE | TRANSACTION_NOTIFY_ROLLBACK 
</td>
</tr>
</table>
 

## -returns
<b>FltEnlistInTransaction</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_ALREADY_ENLISTED</b></dt>
</dl>The caller is already enlisted in the transaction. This is an error code. 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The instance specified in the <i>Instance</i> parameter is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltEnlistInTransaction</b> encountered a pool allocation error. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The caller did not register a <i>TransactionNotificationCallback</i> routine. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>The caller specified an invalid value for the <i>NotificationMask</i> parameter. This is an error code. 

 

## -remarks
A minifilter driver calls <b>FltEnlistInTransaction</b> to enlist in a transaction. Before calling <b>FltEnlistInTransaction</b>, the minifilter driver must have registered a <i>TransactionNotificationCallback</i> routine. Otherwise, the call to <b>FltEnlistInTransaction</b> will fail. 

To register a <i>TransactionNotificationCallback</i> routine, a minifilter driver stores the address of a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> in the <b>TransactionNotificationCallback</b> member of the <a href="ifsk.flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="ifsk.fltregisterfilter">FltRegisterFilter</a>. 

To roll back or abort a transaction, call <a href="ifsk.fltrollbackenlistment">FltRollbackEnlistment</a>. 

To allocate a new transaction context, call <a href="ifsk.fltallocatecontext">FltAllocateContext</a>. 

To retrieve a transaction context, call <a href="ifsk.fltgettransactioncontext">FltGetTransactionContext</a>. 

To delete a transaction context, call <a href="ifsk.fltdeletetransactioncontext">FltDeleteTransactionContext</a> or <a href="ifsk.fltdeletecontext">FltDeleteContext</a>. 

To set a transaction context, call <a href="ifsk.fltsettransactioncontext">FltSetTransactionContext</a>. 

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
This routine is available on Windows Vista and later versions of Windows. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>FltMgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltallocatecontext">FltAllocateContext</a>
</dt>
<dt>
<a href="ifsk.fltcommitcomplete">FltCommitComplete</a>
</dt>
<dt>
<a href="ifsk.fltdeletecontext">FltDeleteContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletetransactioncontext">FltDeleteTransactionContext</a>
</dt>
<dt>
<a href="ifsk.fltgettransactioncontext">FltGetTransactionContext</a>
</dt>
<dt>
<a href="ifsk.fltpreparecomplete">FltPrepareComplete</a>
</dt>
<dt>
<a href="ifsk.fltprepreparecomplete">FltPrePrepareComplete</a>
</dt>
<dt>
<a href="ifsk.fltregisterfilter">FltRegisterFilter</a>
</dt>
<dt>
<a href="ifsk.fltreleasecontext">FltReleaseContext</a>
</dt>
<dt>
<a href="ifsk.fltrollbackcomplete">FltRollbackComplete</a>
</dt>
<dt>
<a href="ifsk.fltrollbackenlistment">FltRollbackEnlistment</a>
</dt>
<dt>
<a href="ifsk.fltsettransactioncontext">FltSetTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnlistInTransaction routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
