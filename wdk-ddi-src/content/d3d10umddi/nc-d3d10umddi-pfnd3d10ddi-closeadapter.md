---
UID: NC.d3d10umddi.PFND3D10DDI_CLOSEADAPTER
title: PFND3D10DDI_CLOSEADAPTER
author: windows-driver-content
description: The CloseAdapter(D3D10) function releases resources for a graphics adapter object.
old-location: display\closeadapter_d3d10_.htm
old-project: display
ms.assetid: bc7ccd91-becc-4596-a56a-562cfe9a18b9
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
req.alt-api: CloseAdapter
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

# PFND3D10DDI_CLOSEADAPTER callback



## -description
<p>The <b>CloseAdapter(D3D10)</b> function releases resources for a graphics adapter object.</p>


## -prototype

````
PFND3D10DDI_CLOSEADAPTER CloseAdapter;

HRESULT APIENTRY CloseAdapter(
  _In_ D3D10DDI_HADAPTER hAdapter
)
{ ... }
````


## -parameters
<dl>

### -param <i>hAdapter</i> [in]

<dd>
<p> A handle to the graphics adapter object that was created with the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-openadapter.md">OpenAdapter10</a> function.</p>
</dd>
</dl>

## -returns
<p><b>CloseAdapter(D3D10)</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. </p>

## -remarks
<p>The user-mode display driver's <b>CloseAdapter(D3D10)</b> function should free all of the resources that the driver allocated for the graphics adapter object.</p>

<p>Before <b>CloseAdapter(D3D10)</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> function will be destroyed in calls to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-destroydevice.md">DestroyDevice(D3D10)</a> function.</p>

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi-adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CLOSEADAPTER callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
