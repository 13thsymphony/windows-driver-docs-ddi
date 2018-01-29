---
UID : NF:fltkernel.FltCompletePendedPreOperation
title : FltCompletePendedPreOperation function
author : windows-driver-content
description : FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine.
old-location : ifsk\fltcompletependedpreoperation.htm
old-project : ifsk
ms.assetid : bdd9f304-b26e-401e-81c7-da7d1e4f5635
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltCompletePendedPreOperation routine [Installable File System Drivers], FLT_PREOP_SUCCESS_WITH_CALLBACK, ifsk.fltcompletependedpreoperation, FltApiRef_a_to_d_170adc13-ea3d-4346-99b2-85d5c1c464b8.xml, FLT_PREOP_SUCCESS_NO_CALLBACK, FLT_PREOP_COMPLETE, fltkernel/FltCompletePendedPreOperation, FltCompletePendedPreOperation
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
req.dll : 
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltCompletePendedPreOperation function
<b>FltCompletePendedPreOperation</b> resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine.

## Syntax

````
VOID FltCompletePendedPreOperation(
  _In_     PFLT_CALLBACK_DATA        Data,
  _In_     FLT_PREOP_CALLBACK_STATUS CallbackStatus,
  _In_opt_ PVOID                     Context
);
````

## Parameters

`CallbackData`

TBD

`CallbackStatus`

The status value that the minifilter driver is returning for this I/O operation. Cannot be FLT_PREOP_PENDING, FLT_PREOP_SYNCHRONIZE, or FLT_PREOP_DISALLOW_FASTIO. Must be one of the following FLT_PREOP_CALLBACK_STATUS values. For more information about the effect of these values, see the Remarks section of the reference entry for <a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>.

`Context`

If FLT_PREOP_SUCCESS_WITH_CALLBACK is specified for <i>CallbackStatus</i>, this parameter is an optional context pointer to be passed to the corresponding postoperation callback routine. If FLT_PREOP_COMPLETE or FLT_PREOP_SUCCESS_NO_CALLBACK is specified for <i>CallbackStatus</i>, this parameter must be <b>NULL</b>.


## Return Value

None

## Remarks

When a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_PREOP_PENDING, the Filter Manager stops processing the operation. When the operation is eventually dequeued and processed, the minifilter driver must call <b>FltCompletePendedPreOperation</b> to return the operation to the Filter Manager, which then resumes processing as directed by the <i>CallbackStatus</i> specified by the minifilter driver. 

If the <i>CallbackStatus</i> parameter is FLT_PREOP_COMPLETE, <b>FltCompletePendedPreOperation</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of <b>FltCompletePendedPreOperation</b> must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md">FltQueueDeferredIoWorkItem</a>

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a>

<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCompletePendedPreOperation routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>