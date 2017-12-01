---
UID: NC.d3dkmddi.DXGKCB_SETPOWERCOMPONENTACTIVE
title: DXGKCB_SETPOWERCOMPONENTACTIVE
author: windows-driver-content
description: Called by the display miniport driver to access a power component.
old-location: display\dxgkcbsetpowercomponentactive.htm
old-project: display
ms.assetid: 12008d80-8bcb-4289-97ea-d3325731a95f
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
req.alt-api: DxgkCbSetPowerComponentActive
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
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DXGKCB_SETPOWERCOMPONENTACTIVE callback



## -description
<p>Called by the display miniport driver to access a power component. After this function returns, the display miniport driver can change the component's hardware settings.</p>


## -prototype

````
DXGKCB_SETPOWERCOMPONENTACTIVE DxgkCbSetPowerComponentActive;

VOID APIENTRY CALLBACK* DxgkCbSetPowerComponentActive(
  _In_ const HANDLE hAdapter,
             UINT   ComponentIndex
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
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>Each call to this function must be paired with a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-setpowercomponentidle.md">DxgkCbSetPowerComponentIdle</a> function to indicate that the component hardware is no longer required.</p>

<p>When this function is called, the active reference count of the component is increased by 1. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.</p>

<p>While calling this function, the display miniport driver might receive a call to the <a href="display.dxgkddisetpowercomponentfstate">DxgkDdiSetPowerComponentFState</a> function on another execution thread.</p>

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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-setpowercomponentidle.md">DxgkCbSetPowerComponentIdle</a>
</dt>
<dt>
<a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="display.dxgkddisetpowercomponentfstate">DxgkDdiSetPowerComponentFState</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SETPOWERCOMPONENTACTIVE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
