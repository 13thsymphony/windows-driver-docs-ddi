---
UID: NC.ndis.MINIPORT_ENABLE_INTERRUPT
title: MINIPORT_ENABLE_INTERRUPT
author: windows-driver-content
description: NDIS can call a miniport driver's MiniportEnableInterruptEx handler to enable interrupts for diagnostic and troubleshooting purposes.
old-location: netvista\miniportenableinterruptex.htm
old-project: netvista
ms.assetid: 61edeb80-a686-4b8c-ae19-4757616151ef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportEnableInterruptEx
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
req.irql: See Remarks section
req.iface: 
---

# MINIPORT_ENABLE_INTERRUPT callback



## -description
<p>NDIS can call a miniport driver's 
   <i>MiniportEnableInterruptEx</i> handler to enable interrupts for diagnostic and troubleshooting
   purposes.</p>


## -prototype

````
MINIPORT_ENABLE_INTERRUPT MiniportEnableInterruptEx;

VOID MiniportEnableInterruptEx(
  _In_ NDIS_HANDLE MiniportInterruptContext
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportInterruptContext</i> [in]

<dd>
<p>A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A miniport driver must provide a
    <i>MiniportEnableInterruptEx</i> handler if the driver calls the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    to register an interrupt.</p>

<p>Miniport drivers should disable and enable interrupts as explained in the 
    <a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a> and 
    <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDpc</a> reference
    pages.</p>

<p>NDIS calls the 
    <i>MiniportEnableInterruptEx</i> and 
    <a href="..\ndis\nc-ndis-miniport-disable-interrupt.md">
    MiniportDisableInterruptEx</a> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableInterruptEx</i> and 
    <i>MiniportDisableInterruptEx</i> access miniport driver resources that are shared by the 
    <a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a> function.
    Therefore, NDIS calls these handlers at DIRQL.</p>

<p>To define a <i>MiniportEnableInterruptEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportEnableInterruptEx</i> function that is named "MyEnableInterruptEx", use the <b>MINIPORT_ENABLE_INTERRUPT</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_ENABLE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ENABLE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<p>See Remarks section</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-disable-interrupt.md">MiniportDisableInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-miniport-interrupt-characteristics.md">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ENABLE_INTERRUPT callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
