---
UID: NC.ndis.PROTOCOL_OPEN_ADAPTER_COMPLETE_EX
title: PROTOCOL_OPEN_ADAPTER_COMPLETE_EX
author: windows-driver-content
description: NDIS calls a protocol driver's ProtocolOpenAdapterCompleteEx function to complete an open adapter operation for which the NdisOpenAdapterEx function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_OPEN_ADAPTER_COMPLETE_EX type. For more information, see the following Examples section.
old-location: netvista\protocolopenadaptercompleteex.htm
ms.assetid: 59d18822-8ce2-4506-90d7-9f1cdc7a9e10
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolOpenAdapterCompleteEx
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: RxNameCacheInitialize
req.iface: 
---

# PROTOCOL_OPEN_ADAPTER_COMPLETE_EX callback



## -description
<p>NDIS calls a protocol driver's 
  <i>ProtocolOpenAdapterCompleteEx</i> function to complete an open adapter operation for which the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function returned
  NDIS_STATUS_PENDING.</p>


## -prototype

````
PROTOCOL_OPEN_ADAPTER_COMPLETE_EX ProtocolOpenAdapterCompleteEx;

VOID ProtocolOpenAdapterCompleteEx(
  _In_ NDIS_HANDLE ProtocolBindingContext,
  _In_ NDIS_STATUS Status
)
{ ... }
````


## -parameters
<dl>

### -param <i>ProtocolBindingContext</i> [in]

<dd>
<p>A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called 
     <b>NdisOpenAdapterEx</b>.</p>
</dd>

### -param <i>Status</i> [in]

<dd>
<p>The final status of the open operation for the underlying miniport driver. This status value is
     NDIS_STATUS_SUCCESS if the binding was established or any error status that the underlying driver
     determines.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The 
    <i>ProtocolOpenAdapterCompleteEx</i> function is required. A protocol driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function from its 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function.
    NDIS calls the driver's 
    <i>ProtocolOpenAdapterCompleteEx</i> function after a pending open operation is complete.</p>

<p>If 
    <i>ProtocolBindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolOpenAdapterCompleteEx</i>, this function can simply save the status and indicate that it has
    been called (for example, it can update the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolBindAdapterEx</i> function to complete the bind operation.</p>

<p>If the 
    <i>ProtocolBindAdapterEx</i> function has not already done so, 
    <i>ProtocolOpenAdapterCompleteEx</i> can allocate the resources that the driver requires for the
    binding.</p>

<p>If
    <i>ProtocolBindAdapterEx</i> returned NDIS_STATUS_PENDING,
    <i>ProtocolOpenAdapterCompleteEx</i> can call the 
    <a href="https://msdn.microsoft.com/e52c7aeb-bbd8-402e-94af-f74df6deb23c">
    NdisCompleteBindAdapterEx</a> function to complete the binding operation. In this case, 
    <i>ProtocolOpenAdapterCompleteEx</i> passes 
    <b>NdisCompleteBindAdapterEx</b> the 
    <i>BindContext</i> handle that NDIS passed to 
    <i>ProtocolBindAdapterEx</i>. If the 
    <i>Status</i> parameter indicates an error, 
    <i>ProtocolOpenAdapterCompleteEx</i> can release binding resources that were set up in 
    <i>ProtocolBindAdapterEx</i>.</p>

<p>NDIS calls 
    <i>ProtocolOpenAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.</p>

<p>To define a <i>ProtocolOpenAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolOpenAdapterCompleteEx</i> function that is named "MyOpenAdapterCompleteEx", use the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p>The 
    <i>ProtocolOpenAdapterCompleteEx</i> function is required. A protocol driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function from its 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function.
    NDIS calls the driver's 
    <i>ProtocolOpenAdapterCompleteEx</i> function after a pending open operation is complete.</p>

<p>If 
    <i>ProtocolBindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolOpenAdapterCompleteEx</i>, this function can simply save the status and indicate that it has
    been called (for example, it can update the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolBindAdapterEx</i> function to complete the bind operation.</p>

<p>If the 
    <i>ProtocolBindAdapterEx</i> function has not already done so, 
    <i>ProtocolOpenAdapterCompleteEx</i> can allocate the resources that the driver requires for the
    binding.</p>

<p>If
    <i>ProtocolBindAdapterEx</i> returned NDIS_STATUS_PENDING,
    <i>ProtocolOpenAdapterCompleteEx</i> can call the 
    <a href="https://msdn.microsoft.com/e52c7aeb-bbd8-402e-94af-f74df6deb23c">
    NdisCompleteBindAdapterEx</a> function to complete the binding operation. In this case, 
    <i>ProtocolOpenAdapterCompleteEx</i> passes 
    <b>NdisCompleteBindAdapterEx</b> the 
    <i>BindContext</i> handle that NDIS passed to 
    <i>ProtocolBindAdapterEx</i>. If the 
    <i>Status</i> parameter indicates an error, 
    <i>ProtocolOpenAdapterCompleteEx</i> can release binding resources that were set up in 
    <i>ProtocolBindAdapterEx</i>.</p>

<p>NDIS calls 
    <i>ProtocolOpenAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.</p>

<p>To define a <i>ProtocolOpenAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolOpenAdapterCompleteEx</i> function that is named "MyOpenAdapterCompleteEx", use the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561702">NdisCompleteBindAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_OPEN_ADAPTER_COMPLETE_EX callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
