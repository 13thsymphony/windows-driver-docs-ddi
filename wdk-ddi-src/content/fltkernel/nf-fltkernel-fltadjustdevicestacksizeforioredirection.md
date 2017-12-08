---
UID: NF.fltkernel.FltAdjustDeviceStackSizeForIoRedirection
title: FltAdjustDeviceStackSizeForIoRedirection function
author: windows-driver-content
description: The FltAdjustDeviceStackSizeForIoRedirection routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack.
old-location: ifsk\fltadjustdevicestacksizeforioredirection.htm
old-project: ifsk
ms.assetid: 48ca0f39-e870-4f9b-92d5-1226972bf2d5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltAdjustDeviceStackSizeForIoRedirection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltAdjustDeviceStackSizeForIoRedirection
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
req.irql: <=DISPATCH_LEVEL
---

# FltAdjustDeviceStackSizeForIoRedirection function



## -description
The <b>FltAdjustDeviceStackSizeForIoRedirection</b> routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack.


## -syntax

````
NTSTATUS FltAdjustDeviceStackSizeForIoRedirection(
  _In_      PFLT_INSTANCE SourceInstance,
  _In_      PFLT_INSTANCE TargetInstance,
  _Out_opt_ PBOOLEAN      SourceDeviceStackSizeModified
);
````


## -parameters

### -param SourceInstance [in]

The filter instance on the source device stack.

### -param TargetInstance [in]

The filter instance on the target device stack.

### -param SourceDeviceStackSizeModified [out, optional]

This optional parameter has a value of <b>TRUE</b> if the <b>FltAdjustDeviceStackSizeForIoRedirection</b> routine modified the size of the source device stack, <b>FALSE</b> otherwise.

## -returns
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>Success.
<dl>
<dt>STATUS_NOT_SUPPORTED</dt>
</dl>The redirection is not supported.
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>The source device stack would be too large after calling this routine.

 

## -remarks
Using <b>FltAdjustDeviceStackSizeForIoRedirection</b> does not guarantee that every IRP that the minifilter encounters will be sufficient in size to be redirected to the target stack. IRPs that were allocated and issued before the call to <b>FltAdjustDeviceStackSizeForIoRedirection</b> would still have been allocated based on the old stack size. 

A minifilter can adjust the stack size during instance setup if the filter knows which stack the I/O will be redirected to. 

The filter can issue its own create operation down the new stack using <a href="ifsk.fltcreatefile">FltCreateFile</a>. Before completing the create operation, the filter can adjust the stack size to account for the target stack. Doing that adjustment ensures that the stack size will be adjusted before the create action is completed. All IRPs allocated for that file object will have a large enough stack to support redirection.

During instance-setup or during post-create callback for a redirected file object, use <a href="ifsk.fltisioredirectionallowed">FltIsIoRedirectionAllowed</a> to determine if redirection is possible without modifying the source stack. If necessary, use <b>FltAdjustDeviceStackSizeForIoRedirection</b> to adjust the source stack.

In the pre-operation callback for every operation that needs redirection, use <a href="ifsk.fltisioredirectionallowedforoperation">FltIsIoRedirectionAllowedForOperation</a> to determine if redirection is possible without modifying the source stack. If necessary, use <b>FltAdjustDeviceStackSizeForIoRedirection</b> to adjust the source stack.

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
Available in Windows 7 and later versions of the Windows operating system.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>FltKernel.h (include FltKernel.h)</dt>
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
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>
</dt>
<dt>
<a href="ifsk.fltisioredirectionallowed">FltIsIoRedirectionAllowed</a>
</dt>
<dt>
<a href="ifsk.fltisioredirectionallowedforoperation">FltIsIoRedirectionAllowedForOperation</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAdjustDeviceStackSizeForIoRedirection routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
