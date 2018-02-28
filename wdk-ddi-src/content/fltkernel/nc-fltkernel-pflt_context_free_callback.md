---
UID: NC:fltkernel.PFLT_CONTEXT_FREE_CALLBACK
title: PFLT_CONTEXT_FREE_CALLBACK
author: windows-driver-content
description: A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's ContextFreeCallback routine.
old-location: ifsk\pflt_context_free_callback.htm
old-project: ifsk
ms.assetid: 11c397c2-51a5-4acd-8029-cd002f990366
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ContextFreeCallback, ContextFreeCallback routine [Installable File System Drivers], FltCallbacks_c7e2b5e1-5666-431c-9032-59914ef23336.xml, PFLT_CONTEXT_FREE_CALLBACK, fltkernel/ContextFreeCallback, ifsk.pflt_context_free_callback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	ContextFreeCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# PFLT_CONTEXT_FREE_CALLBACK callback function
A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's <i>ContextFreeCallback</i> routine.

## Syntax

```
PFLT_CONTEXT_FREE_CALLBACK PfltContextFreeCallback;

void PfltContextFreeCallback(
  PVOID Pool,
  FLT_CONTEXT_TYPE ContextType
)
{...}
```

## Parameters

`Pool`

A pointer to the context to be freed.

`ContextType`

The type of context. This parameter is required and must be one of the following values: 

FLT_FILE_CONTEXT (starting with  Windows Vista)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_SECTION_CONTEXT (starting with Windows 8)

FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

FLT_VOLUME_CONTEXT


## Return Value

None.

## Remarks

For the rare cases that a minifilter driver must free its own contexts manually, the minifilter driver can specify a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's <i>ContextFreeCallback</i> routine for each context type that it registers when it calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextFreeCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

For more information about context registration, see the reference entry for <a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **IRQL** | "<=APC_LEVEL" |

## See Also

<a href="..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>



<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



<a href="..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md">PFLT_CONTEXT_CLEANUP_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_CONTEXT_FREE_CALLBACK routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>