---
UID: NC:wdfrequest.PFN_WDFREQUESTSETCOMPLETIONROUTINE
title: PFN_WDFREQUESTSETCOMPLETIONROUTINE function
author: windows-driver-content
description: The WdfRequestSetCompletionRoutine method registers or deregisters a completion routine for the specified framework request object.
old-location: wdf\wdfrequestsetcompletionroutine.htm
old-project: wdf
ms.assetid: c60f3dd5-2a74-4d7c-8804-35b9dd91dce4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFREQUESTSETCOMPLETIONROUTINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestSetCompletionRoutine
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqCompletionRoutine
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTSETCOMPLETIONROUTINE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSetCompletionRoutine</b> method registers or deregisters a completion routine for the specified framework request object.



## -syntax

````
VOID WdfRequestSetCompletionRoutine(
  _In_     WDFREQUEST                         Request,
  _In_opt_ PFN_WDF_REQUEST_COMPLETION_ROUTINE CompletionRoutine,
  _In_opt_ WDFCONTEXT                         CompletionContext
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param CompletionRoutine [in, optional]

A pointer to a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, if the driver is registering a completion routine, or <b>NULL</b> of the driver is deregistering a previously registered completion routine.


### -param CompletionContext [in, optional]

An untyped pointer to driver-defined context information that the framework passes to the <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If your driver forwards I/O requests, but if you want your driver to be notified when a lower-level driver completes the request, your driver can provide a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function and call <b>WdfRequestSetCompletionRoutine</b> to register the function. The framework calls the callback function after a lower-level driver completes the I/O request. 

For more information about <b>WdfRequestSetCompletionRoutine</b>, see <a href="https://msdn.microsoft.com/ec5aef7a-110e-430c-902d-669ccc7095ac">Completing I/O Requests</a>.

For a code example that uses <b>WdfRequestSetCompletionRoutine</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551579">ReqCompletionRoutine</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetCompletionRoutine method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

