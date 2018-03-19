---
UID: NF:fltkernel.FltClearCancelCompletion
title: FltClearCancelCompletion function
author: windows-driver-content
description: FltClearCancelCompletion clears a cancel routine that was specified for an I/O operation.
old-location: ifsk\fltclearcancelcompletion.htm
old-project: ifsk
ms.assetid: 75c66cb7-3378-4951-9180-d1bd9f201a42
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_4dea0214-a0a2-45b8-b044-960881a8f065.xml, FltClearCancelCompletion, FltClearCancelCompletion routine [Installable File System Drivers], fltkernel/FltClearCancelCompletion, ifsk.fltclearcancelcompletion
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
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltClearCancelCompletion
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltClearCancelCompletion function
<b>FltClearCancelCompletion</b> clears a cancel routine that was specified for an I/O operation.

## Syntax

````
NTSTATUS FltClearCancelCompletion(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````

## Parameters

`CallbackData`

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation.


## Return Value

If no cancel routine was previously set or if IRP cancellation is already in progress, <b>FltClearCancelCompletion</b> returns STATUS_CANCELLED. Otherwise, it returns STATUS_SUCCESS.

## Remarks

A minifilter driver calls <b>FltClearCancelCompletion</b> to clear a cancel routine that was specified for an I/O operation by a previous call to <a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>. The operation must be an IRP-based I/O operation. To determine whether a given callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

To cancel an I/O operation, call <a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>