---
UID: NF:fltkernel.FltGetTransactionContext
title: FltGetTransactionContext function
author: windows-driver-content
description: The FltGetTransactionContext routine retrieves a context that was set for a transaction by a given minifilter driver.
old-location: ifsk\fltgettransactioncontext.htm
old-project: ifsk
ms.assetid: fcd41baf-43ff-4f3a-8211-9fb5cb1cd2fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_11458006-a870-473b-9d1b-ab7a97af09b3.xml, FltGetTransactionContext, FltGetTransactionContext routine [Installable File System Drivers], fltkernel/FltGetTransactionContext, ifsk.fltgettransactioncontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltGetTransactionContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetTransactionContext function
The <b>FltGetTransactionContext</b> routine retrieves a context that was set for a transaction by a given minifilter driver.

## Syntax

````
NTSTATUS FltGetTransactionContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PKTRANSACTION Transaction,
  _Out_ PFLT_CONTEXT  *Context
);
````

## Parameters

`Instance`

Opaque instance pointer for the caller.

`Transaction`

Opaque transaction pointer for the transaction whose context is being retrieved.

`Context`

Pointer to a caller-allocated variable that receives the address of the transaction context.


## Return Value

<b>FltGetTransactionContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
No matching context was found. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltGetTransactionContext</b> is available on Windows Vista and later. 

<b>FltGetTransactionContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. Thus every successful call to <b>FltGetTransactionContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a transaction, call <a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>. 

To allocate a new transaction context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a transaction context, call <a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | FltMgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltprepreparecomplete.md">FltPrePrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackcomplete.md">FltRollbackComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltpreparecomplete.md">FltPrepareComplete</a>



<a href="..\fltkernel\nf-fltkernel-fltrollbackenlistment.md">FltRollbackEnlistment</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltenlistintransaction.md">FltEnlistInTransaction</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>



<a href="..\fltkernel\nf-fltkernel-fltcommitcomplete.md">FltCommitComplete</a>