---
UID: NC.d3d10umddi.PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS
author: windows-driver-content
description: The CheckMultisampleQualityLevels function retrieves the number of quality levels that the device supports for the specified number of samples.
old-location: display\checkmultisamplequalitylevels.htm
old-project: display
ms.assetid: 2b6a0ab8-f197-48c3-baf2-305b77b7e8b5
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
req.alt-api: CheckMultisampleQualityLevels
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

# PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback



## -description
<p>The <b>CheckMultisampleQualityLevels</b> function retrieves the number of quality levels that the device supports for the specified number of samples. </p>


## -prototype

````
PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS CheckMultisampleQualityLevels;

VOID APIENTRY CheckMultisampleQualityLevels(
  _In_  D3D10DDI_HDEVICE hDevice,
  _In_  DXGI_FORMAT      Format,
  _In_  UINT             SampleCount,
  _Out_ UINT             *pNumQualityLevels
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param Format [in]

<dd>
<p> A DXGI_FORMAT-typed value that indicates the render-target format that the check is performed for. </p>
</dd>

### -param SampleCount [in]

<dd>
<p> The number of samples to retrieve the quality levels for. </p>
</dd>

### -param pNumQualityLevels [out]

<dd>
<p>A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples. </p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_INVALIDARG if the format in the <i>Format</i> parameter does not exist or the <i>pNumQualityLevels</i> parameter is <b>NULL</b>.</p>

## -remarks
<p>If the device does not support multiple sampling with the number of samples that is specified in the <i>SampleCount</i> parameter, the user-mode display driver should return 0 in the variable that the <i>pNumQualityLevels</i> parameter points to.</p>

<p>When the driver returns 1 or more in the variable that <i>pNumQualityLevels</i> points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.</p>

<p>If the driver receives 1 in <i>SampleCount</i>, the driver always returns 1 in the variable that <i>pNumQualityLevels</i> points to.</p>

<p>If the driver receives 0 or greater than 32 in <i>SampleCount</i>, the driver always returns 0 in the variable that <i>pNumQualityLevels</i> points to. </p>

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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi-devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
