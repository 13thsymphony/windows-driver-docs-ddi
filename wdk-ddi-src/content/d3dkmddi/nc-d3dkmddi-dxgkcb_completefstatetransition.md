---
UID: NC:d3dkmddi.DXGKCB_COMPLETEFSTATETRANSITION
title: DXGKCB_COMPLETEFSTATETRANSITION
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition.
old-location: display\dxgkcbcompletefstatetransition.htm
old-project: display
ms.assetid: 69a6d9bc-44a9-4204-988e-e11c80f67f28
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbCompleteFStateTransition
req.alt-loc: D3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_COMPLETEFSTATETRANSITION callback



## -description
Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition.



## -prototype

````
DXGKCB_COMPLETEFSTATETRANSITION DxgkCbCompleteFStateTransition;

VOID APIENTRY CALLBACK* DxgkCbCompleteFStateTransition(
  _In_ const HANDLE hAdapter,
             UINT   ComponentIndex
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param ComponentIndex 

The power component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -returns
This callback function does not return a value.


## -remarks
During component registration the display miniport driver should indicate all power components for which it will need to call the <i>DxgkCbCompleteFStateTransition</i> function by setting the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_component_flags.md">DXGK_POWER_COMPONENT_FLAGS</a>.<b>DriverCompletesFStateTransition</b> member to 1. When this member is set, the driver must call this function either synchronously or asynchronously. Conversely, if this member is not set, the driver should not call this function.

The Windows power management framework guarantees that no new transition request will be sent for the component until this function is called.

Usually the port driver expects that when this function returns, the F-state transition is completed. There could be scenarios when the display miniport driver cannot complete the transition synchronously, for example if the display miniport driver cannot complete the transitions at <b>DISPATCH_LEVEL</b>, or it needs to activate other power components. This function helps the display miniport driver to complete the F-state transition asynchronously.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
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
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_component_flags.md">DXGK_POWER_COMPONENT_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_COMPLETEFSTATETRANSITION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

