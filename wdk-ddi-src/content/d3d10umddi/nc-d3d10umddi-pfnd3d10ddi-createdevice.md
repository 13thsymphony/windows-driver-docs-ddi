---
UID: NC.d3d10umddi.PFND3D10DDI_CREATEDEVICE
title: PFND3D10DDI_CREATEDEVICE
author: windows-driver-content
description: The CreateDevice(D3D10) function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice_d3d10_.htm
old-project: display
ms.assetid: c69eedb1-c975-412c-aa9f-cf64a702f937
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateDevice
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

# PFND3D10DDI_CREATEDEVICE callback



## -description
<p>The <b>CreateDevice(D3D10)</b> function creates a graphics context that is referenced in subsequent calls. </p>


## -prototype

````
PFND3D10DDI_CREATEDEVICE CreateDevice;

HRESULT APIENTRY CreateDevice(
          D3D10DDI_HADAPTER        hAdapter,
  _Inout_ D3D10DDIARG_CREATEDEVICE *pCreateData
)
{ ... }
````


## -parameters
<dl>

### -param hAdapter 

<dd>
<p> A handle to the graphics adapter object that was created with the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-openadapter.md">OpenAdapter10</a> function.</p>
</dd>

### -param pCreateData [in, out]

<dd>
<p>A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.</p>
</dd>
</dl>

## -returns
<p><b>CreateDevice(D3D10)</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The graphics context was successfully created.</p><dl>
<dt><b>DXGI_STATUS_NO_REDIRECTION</b></dt>
</dl><p>The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> could not allocate the memory that was required for it to complete.</p>

<p> </p>

## -remarks
<p>A display device is a graphics context that is used to hold a collection of rendering state. The same process can create multiple devices on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.</p>

<p>Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.</p>

## -requirements
<table>
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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi-adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createdevice.md">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-destroydevice.md">DestroyDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-openadapter.md">OpenAdapter10</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEDEVICE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
