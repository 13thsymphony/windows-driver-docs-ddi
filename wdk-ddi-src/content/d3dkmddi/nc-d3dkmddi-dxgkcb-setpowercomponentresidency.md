---
UID: NC.d3dkmddi.DXGKCB_SETPOWERCOMPONENTRESIDENCY
title: DXGKCB_SETPOWERCOMPONENTRESIDENCY
author: windows-driver-content
description: Called by the display miniport driver to set the expected residency for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentresidency.htm
old-project: display
ms.assetid: 9D567380-2E77-4A63-8674-E19A13C7B8BC
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DxgkCbSetPowerComponentResidency
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
req.iface: 
---

# DXGKCB_SETPOWERCOMPONENTRESIDENCY callback



## -description
<p>Called by the display miniport driver to set the expected residency for a power component of type <b>DXGK_POWER_COMPONENT_OTHER</b>.</p>


## -prototype

````
DXGKCB_SETPOWERCOMPONENTRESIDENCY DxgkCbSetPowerComponentResidency;

VOID APIENTRY CALLBACK* DxgkCbSetPowerComponentResidency(
  _In_ const HANDLE    hAdapter,
             UINT      ComponentIndex,
             ULONGLONG Residency
)
{ ... }
````


## -parameters
<dl>

### -param <i>hAdapter</i> [in]

<dd>
<p>A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt--dxgkrnl-interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a> function.</p>
</dd>

### -param <i>ComponentIndex</i> 

<dd>
<p>The power component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.</p>
</dd>

### -param <i>Residency</i> 

<dd>
<p>The <i>expected residency</i>—the maximum  time, in units of 100 nanoseconds, that the display miniport driver expects a power component to remain idle after it enters an idle state. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> uses this information to select an appropriate idle state for the component that does not violate the requested residency. The expected residency specified by <i>Residency</i> remains in effect until the driver calls this function again to update it.</p>
<p>For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>If the power component is in an idle state when this function is called, the <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> might change the component's F-state to meet the expected residency value specified by <i>Residency</i>.</p>

<p>If the driver sets <i>Residency</i> to a value of <b>PO_FX_UNKNOWN_TIME</b> (defined in Wdm.h), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
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
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt--dxgkrnl-interface.md">DXGKRNL_INTERFACE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SETPOWERCOMPONENTRESIDENCY callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
