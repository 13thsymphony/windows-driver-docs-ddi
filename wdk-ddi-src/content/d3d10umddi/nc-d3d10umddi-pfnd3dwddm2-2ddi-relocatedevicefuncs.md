---
UID: NC.d3d10umddi.PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The pfnRelocateDeviceFuncs callback function specifies the device functions table.
old-location: display\pfnd3dwddm2_2ddi_relocatedevicefuncs.htm
old-project: display
ms.assetid: EAABE65C-3893-4B4C-BB7E-A02F91F869BE
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnRelocateDeviceFuncs
req.alt-loc: d3d10umddi.h
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
---

# PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback



## -description
<p>The <i>pfnRelocateDeviceFuncs</i> callback function specifies the device functions table. </p>


## -prototype

````
PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS pfnRelocateDeviceFuncs;

VOID APIENTRY* pfnRelocateDeviceFuncs(
       D3D10DDI_HDEVICE          hDevice,
  _In_ D3DWDDM2_2DDI_DEVICEFUNCS *DeviceFunctions
)
{ ... }
````


## -parameters
<dl>

### -param hDevice 

<dd>
<p>The handle of a device.</p>
</dd>

### -param DeviceFunctions [in]

<dd>
<p>The device functions table, as a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2-2ddi-devicefuncs~r1.md">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2-2ddi-devicefuncs~r1.md">D3DWDDM2_2DDI_DEVICEFUNCS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
