---
UID: NF.fltkernel.FltCompletePendedPreOperation
title: FltCompletePendedPreOperation function
author: windows-driver-content
description: FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine.
old-location: ifsk\fltcompletependedpreoperation.htm
old-project: ifsk
ms.assetid: bdd9f304-b26e-401e-81c7-da7d1e4f5635
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltCompletePendedPreOperation
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
req.alt-api: FltCompletePendedPreOperation
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: See Remarks section.
---

# FltCompletePendedPreOperation function



## -description
<b>FltCompletePendedPreOperation</b> resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine. 



## -syntax

````
VOID FltCompletePendedPreOperation(
  _In_     PFLT_CALLBACK_DATA        Data,
  _In_     FLT_PREOP_CALLBACK_STATUS CallbackStatus,
  _In_opt_ PVOID                     Context
);
````


## -parameters

### -param Data [in]

Pointer to the callback data (<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param CallbackStatus [in]

The status value that the minifilter driver is returning for this I/O operation. Cannot be FLT_PREOP_PENDING, FLT_PREOP_SYNCHRONIZE, or FLT_PREOP_DISALLOW_FASTIO. Must be one of the following FLT_PREOP_CALLBACK_STATUS values. For more information about the effect of these values, see the Remarks section of the reference entry for <a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>. 


### -param FLT_PREOP_COMPLETE

<dd>
The minifilter driver is completing the I/O operation. The Filter Manager does not send the I/O operation to any minifilter drivers below the caller or to the file system. The Filter Manager only calls the postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routines of the minifilter drivers above the caller. 


### -param FLT_PREOP_SUCCESS_NO_CALLBACK

<dd>
The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager does not call the corresponding postoperation callback, if one exists, during I/O completion. 


### -param FLT_PREOP_SUCCESS_WITH_CALLBACK

<dd>
The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager calls the corresponding postoperation callback during I/O completion. 

</dd>
</dl>

### -param Context [in, optional]

If FLT_PREOP_SUCCESS_WITH_CALLBACK is specified for <i>CallbackStatus</i>, this parameter is an optional context pointer to be passed to the corresponding postoperation callback routine. If FLT_PREOP_COMPLETE or FLT_PREOP_SUCCESS_NO_CALLBACK is specified for <i>CallbackStatus</i>, this parameter must be <b>NULL</b>. 


## -returns
None 


## -remarks
When a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_PREOP_PENDING, the Filter Manager stops processing the operation. When the operation is eventually dequeued and processed, the minifilter driver must call <b>FltCompletePendedPreOperation</b> to return the operation to the Filter Manager, which then resumes processing as directed by the <i>CallbackStatus</i> specified by the minifilter driver. 

If the <i>CallbackStatus</i> parameter is FLT_PREOP_COMPLETE, <b>FltCompletePendedPreOperation</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of <b>FltCompletePendedPreOperation</b> must be running at IRQL &lt;= APC_LEVEL. 


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
IRQL

</th>
<td width="70%">
See Remarks section.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.fltcbdqinitialize">FltCbdqInitialize</a>
</dt>
<dt>
<a href="ifsk.fltcompletependedpostoperation">FltCompletePendedPostOperation</a>
</dt>
<dt>
<a href="ifsk.fltqueuedeferredioworkitem">FltQueueDeferredIoWorkItem</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCompletePendedPreOperation routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

