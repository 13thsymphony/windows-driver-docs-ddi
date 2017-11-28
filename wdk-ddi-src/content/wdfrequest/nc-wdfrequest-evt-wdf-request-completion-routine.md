---
UID: NC.wdfrequest.EVT_WDF_REQUEST_COMPLETION_ROUTINE
title: EVT_WDF_REQUEST_COMPLETION_ROUTINE
author: windows-driver-content
description: A driver's CompletionRoutine event callback function executes when another driver completes a specified I/O request.
old-location: wdf\completionroutine.htm
old-project: wdf
ms.assetid: 7d3eb4d6-9fc7-4924-9b95-f5824713049b
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WdfRegistryWdmGetHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: CompletionRoutine
req.alt-loc: Wdfrequest.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_REQUEST_COMPLETION_ROUTINE callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>A driver's <i>CompletionRoutine</i> event callback function executes when another driver completes a specified I/O request.</p>


## -prototype

````
EVT_WDF_REQUEST_COMPLETION_ROUTINE CompletionRoutine;

void CompletionRoutine(
  _In_ WDFREQUEST                     Request,
  _In_ WDFIOTARGET                    Target,
  _In_ PWDF_REQUEST_COMPLETION_PARAMS Params,
  _In_ WDFCONTEXT                     Context
)
{ ... }
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object that represents the completed I/O request.</p>
</dd>

### -param <i>Target</i> [in]

<dd>
<p>A handle to an I/O target object that represents the I/O target that completed the request.</p>
</dd>

### -param <i>Params</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure that contains information about the completed request.</p>
</dd>

### -param <i>Context</i> [in]

<dd>
<p>Driver-supplied context information, which the driver specified in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="wdf.completing_i_o_requests">Completing I/O Requests</a>.</p>

<p>Note that the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For an example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548612">WdfIoTargetFormatRequestForRead</a>.</p>

<p>A KMDF driver's <i>CompletionRoutine</i> can run at IRQL &lt;= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  </p>

<p>The function type is declared in <i>Wdfrequest.h</i>, as follows.</p>

<p>To define a <i>CompletionRoutine</i> callback function that is named <b>MyCompletionRoutine</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

<p>To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="wdf.completing_i_o_requests">Completing I/O Requests</a>.</p>

<p>Note that the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For an example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548612">WdfIoTargetFormatRequestForRead</a>.</p>

<p>A KMDF driver's <i>CompletionRoutine</i> can run at IRQL &lt;= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  </p>

<p>The function type is declared in <i>Wdfrequest.h</i>, as follows.</p>

<p>To define a <i>CompletionRoutine</i> callback function that is named <b>MyCompletionRoutine</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

<p>To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="wdf.completing_i_o_requests">Completing I/O Requests</a>.</p>

<p>Note that the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For an example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548612">WdfIoTargetFormatRequestForRead</a>.</p>

<p>A KMDF driver's <i>CompletionRoutine</i> can run at IRQL &lt;= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  </p>

<p>The function type is declared in <i>Wdfrequest.h</i>, as follows.</p>

<p>To define a <i>CompletionRoutine</i> callback function that is named <b>MyCompletionRoutine</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_REQUEST_COMPLETION_ROUTINE callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
