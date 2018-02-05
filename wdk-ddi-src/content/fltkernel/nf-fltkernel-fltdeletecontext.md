---
UID : NF:fltkernel.FltDeleteContext
title : FltDeleteContext function
author : windows-driver-content
description : FltDeleteContext marks a specified context for deletion.
old-location : ifsk\fltdeletecontext.htm
old-project : ifsk
ms.assetid : 1cdb0747-7616-414b-8287-1ef73637ed05
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fltkernel/FltDeleteContext, FltDeleteContext function [Installable File System Drivers], FltDeleteContext, FltApiRef_a_to_d_d4c075e6-7a69-4d2f-9017-eccbf55eb9e0.xml, ifsk.fltdeletecontext
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltDeleteContext function
<b>FltDeleteContext</b> marks a specified context for deletion.

## Syntax

````
VOID FltDeleteContext(
  _In_ PFLT_CONTEXT Context
);
````

## Parameters

`Context`

A pointer to the context to delete. This parameter is required and cannot be <b>NULL</b>.


## Return Value

None.

## Remarks

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine, such as <b>FltDeleteContext</b>, to explicitly delete a context. 

<b>FltDeleteContext</b> marks a context for deletion. The context is usually freed as soon as the current reference on it is released, unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

You should consider the following items when you use <b>FltDeleteContext</b>:
<ul>
<li>
When a minifilter driver calls <b>FltDeleteContext</b>, the minifilter driver must already have a reference to the context. However, when the minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md">FltDeleteStreamHandleContext</a>, <a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>, <a href="..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md">FltDeleteInstanceContext</a>, and so on, the minifilter driver does not require a reference to the context. After the minifilter driver calls <b>FltDeleteContext</b>, that reference to the context is still valid. The minifilter driver must call the <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> routine to release the reference to the context. 

</li>
<li>
<b>FltDeleteContext</b> removes the context from the internal filter manager structures. Then, further calls to functions that retrieve contexts, such as  <a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a> and <a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>, cannot locate that context. However, the context memory is not released until the reference count for the context goes to 0. 

</li>
</ul>Contexts can also be deleted by calling the appropriate delete-context routine from the following table. 
<table>
<tr>
<th>Context Type</th>
<th>Delete-Context Routine</th>
</tr>
<tr>
<td>
FLT_FILE_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a> (Windows Vista and later only.)

</td>
</tr>
<tr>
<td>
FLT_INSTANCE_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md">FltDeleteInstanceContext</a>


</td>
</tr>
<tr>
<td>
FLT_SECTION_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a> (Windows 8 and later only.)

</td>
</tr>
<tr>
<td>
FLT_STREAM_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>


</td>
</tr>
<tr>
<td>
FLT_STREAMHANDLE_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md">FltDeleteStreamHandleContext</a>


</td>
</tr>
<tr>
<td>
FLT_TRANSACTION_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> (Windows Vista and later only.)

</td>
</tr>
<tr>
<td>
FLT_VOLUME_CONTEXT

</td>
<td>

<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>


</td>
</tr>
</table> 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To increment the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>. 

To decrement the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

A section context, FLT_SECTION_CONTEXT type, must not be deleted using <b>FltDeleteContext</b>. Instead, use  <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to deallocate a section context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a>

<a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>

<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a>

<a href="..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md">FltDeleteInstanceContext</a>

<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md">FltDeleteStreamHandleContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>