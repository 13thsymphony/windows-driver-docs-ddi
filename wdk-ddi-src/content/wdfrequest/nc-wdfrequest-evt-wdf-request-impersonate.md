---
UID: NC.wdfrequest.EVT_WDF_REQUEST_IMPERSONATE
title: EVT_WDF_REQUEST_IMPERSONATE
author: windows-driver-content
description: A driver's EvtRequestImpersonate event callback function performs tasks at the requested impersonation level, such as opening a protected file.
old-location: wdf\evtrequestimpersonate.htm
old-project: wdf
ms.assetid: FA3FE0C0-57EC-4761-991B-49CA65A79BDD
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WdfRegistryWdmGetHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: EvtRequestImpersonate
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
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_REQUEST_IMPERSONATE callback



## -description
<p class="CCE_Message">[Applies to UMDF only]</p>
<p>A driver's <i>EvtRequestImpersonate</i> event callback function performs tasks at the requested impersonation level, such as opening a protected file.</p>


## -prototype

````
EVT_WDF_REQUEST_IMPERSONATE EvtRequestImpersonate;

void EvtRequestImpersonate(
  _In_     WDFREQUEST Request,
  _In_opt_ PVOID      Context
)
{ ... }
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object that represents the I/O request that requires impersonation.</p>
</dd>

### -param <i>Context</i> [in, optional]

<dd>
<p>A pointer to a context that was previously supplied in the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestimpersonate.md">WdfRequestImpersonate</a> method. This parameter is optional and can be NULL if a context is not required. 

</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>User-Mode Driver Framework (UMDF) does not allow a driver's <i>EvtRequestImpersonate</i> callback function to call any of the framework's object methods. This ensures that the driver does not expose the impersonation level to other driver callback functions or other drivers.</p>

<p>For more information, see <a href="wdf.handling_client_impersonation_in_umdf_drivers">Handling Client Impersonation in UMDF Drivers</a>.</p>

<p>To define an <i>EvtRequestImpersonate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtRequestImpersonate</i> callback function that is named <i>MyRequestImpersonate</i>, use the <b>EVT_WDF_REQUEST_IMPERSONATE</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_REQUEST_IMPERSONATE</b> function type is defined in the Wdfrequest.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_REQUEST_IMPERSONATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<p>Minimum support</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestimpersonate.md">WdfRequestImpersonate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_REQUEST_IMPERSONATE callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
