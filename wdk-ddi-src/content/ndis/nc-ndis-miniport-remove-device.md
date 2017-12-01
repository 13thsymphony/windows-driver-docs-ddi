---
UID: NC.ndis.MINIPORT_REMOVE_DEVICE
title: MINIPORT_REMOVE_DEVICE
author: windows-driver-content
description: The MiniportRemoveDevice function releases resources that the MiniportAddDevice function allocated.
old-location: netvista\miniportremovedevice.htm
old-project: netvista
ms.assetid: 24dd887b-575f-4790-bb53-7c3fb825bd61
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
req.alt-api: MiniportRemoveDevice
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
req.iface: 
---

# MINIPORT_REMOVE_DEVICE callback



## -description
<p>The 
   <i>MiniportRemoveDevice</i> function releases resources that the 
   <a href="..\ndis\nc-ndis-miniport-add-device.md">MiniportAddDevice</a> function
   allocated.</p>


## -prototype

````
MINIPORT_REMOVE_DEVICE MiniportRemoveDevice;

VOID MiniportRemoveDevice(
  _In_ NDIS_HANDLE MiniportAddDeviceContext
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportAddDeviceContext</i> [in]

<dd>
<p>A handle for a driver-allocated context area that the miniport driver registered with NDIS in the 
     <a href="..\ndis\nc-ndis-miniport-add-device.md">MiniportAddDevice</a> function.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The 
    <i>MiniportRemoveDevice</i> function is an optional function. Miniport drivers that
    support MSI-X should specify an entry point for this function in the 
    <a href="..\ndis\ns-ndis--ndis-miniport-pnp-characteristics.md">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure.</p>

<p>When NDIS receives a request from the Plug and Play (PnP) manager to remove a device, NDIS calls the 
    <i>MiniportRemoveDevice</i> function. 
    <i>MiniportRemoveDevice</i> should then undo the operations that the 
    <a href="..\ndis\nc-ndis-miniport-add-device.md">MiniportAddDevice</a> function
    performed.</p>

<p>Miniport adapters might be halted and initialized several times before NDIS calls 
    <i>MiniportRemoveDevice</i>. If NDIS called 
    <i>MiniportAddDevice</i> and it returned NDIS_STATUS_SUCCESS, NDIS will not call 
    <i>MiniportAddDevice</i> for the same miniport adapter before calling 
    <i>MiniportRemoveDevice</i> for that adapter.</p>

<p>NDIS calls 
    <i>MiniportRemoveDevice</i> at IRQL = PASSIVE_LEVEL.</p>

<p>To define a <i>MiniportRemoveDevice</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportRemoveDevice</i> function that is named "MyRemoveDevice", use the <b>MINIPORT_REMOVE_DEVICE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_REMOVE_DEVICE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_REMOVE_DEVICE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<a href="..\ndis\nc-ndis-miniport-add-device.md">MiniportAddDevice</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-miniport-init-parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-miniport-pnp-characteristics.md">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_REMOVE_DEVICE callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
