---
UID: NF:fltkernel.FltReleaseContext
title: FltReleaseContext function
author: windows-driver-content
description: FltReleaseContext decrements the reference count on a context.
old-location: ifsk\fltreleasecontext.htm
old-project: ifsk
ms.assetid: b0585443-b8e9-41bc-81af-5707fda2465d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltReleaseContext
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
req.alt-api: FltReleaseContext
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: See Remarks section.
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# FltReleaseContext function



## -description
<b>FltReleaseContext</b> decrements the reference count on a context. 



## -syntax

````
VOID FltReleaseContext(
  _In_ PFLT_CONTEXT Context
);
````


## -parameters

### -param Context [in]

Pointer to the context. Must be a valid pointer to a context object for a volume, instance, stream, or stream handle. This parameter is required and cannot be <b>NULL</b>. 


## -returns
None 


## -remarks
A minifilter driver calls <b>FltReleaseContext</b> to release a context. <b>FltReleaseContext</b> decrements the reference count on the given context. When the reference count reaches zero, the context is freed immediately if the caller is running at IRQL &lt;= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context. 

Every successful call to <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>, <b>FltGet</b><i>Xxx</i><b>Context</b>, or <a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a> must eventually be matched by a call to <b>FltReleaseContext</b>. 

Note that the <i>OldContext</i> pointer returned by <b>FltSet</b><i>Xxx</i><b>Context</b> and the <i>Context</i> parameter that is used to call <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a> must also be released by calling <b>FltReleaseContext</b> when they are no longer needed. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To increment the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

Callers of <b>FltReleaseContext</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the context was allocated from nonpaged pool. If the context was allocated from paged pool, callers must be running at IRQL &lt;= APC_LEVEL. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md">FltGetStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontexts.md">FltReleaseContexts</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetinstancecontext.md">FltSetInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetstreamhandlecontext.md">FltSetStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReleaseContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

