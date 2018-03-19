---
UID: NC:d3d10umddi.PFND3D10DDI_RETRIEVESUBOBJECT
title: PFND3D10DDI_RETRIEVESUBOBJECT
author: windows-driver-content
description: Retrieves subparts of the Microsoft Direct3D driver device object.
old-location: display\retrievesubobject_d3d11_1_.htm
old-project: display
ms.assetid: 9029ec8d-102f-4d83-8ab5-fc208d8b5249
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_RETRIEVESUBOBJECT, RetrieveSubObject(D3D11_1), RetrieveSubObject(D3D11_1) callback function [Display Devices], d3d10umddi/RetrieveSubObject(D3D11_1), display.retrievesubobject, display.retrievesubobject_d3d11_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	RetrieveSubObject(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_RETRIEVESUBOBJECT callback function
Retrieves subparts of the Microsoft Direct3D driver device object.

## Syntax

```
PFND3D10DDI_RETRIEVESUBOBJECT Pfnd3d10ddiRetrievesubobject;

HRESULT Pfnd3d10ddiRetrievesubobject(
   D3D10DDI_HDEVICE,
  UINT32 SubDeviceID,
  SIZE_T ParamSize,
  void *pParams,
  SIZE_T OutputParamSize,
  void *pOutputParamsBuffer
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`SubDeviceID`

The function table being retrieved, with the following possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
A video function table that is described as a   structure. The function returns a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md">D3D11_1DDI_VIDEODEVICEFUNCS</a> structure in the buffer referenced by the <i>pOutputParamsBuffer</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3</dt>
</dl>
</td>
<td width="60%">
A WDDM 2.0 and later video function table that is described as a   structure. The function returns a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs.md">D3DWDDM2_0DDI_VIDEODEVICEFUNCS</a> structure in the buffer referenced by the <i>pOutputParamsBuffer</i> parameter.

Supported starting with WDDM 2.0.

</td>
</tr>
</table>

`ParamSize`

The size, in bytes, of an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

`*pParams`

A pointer to an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

`OutputParamSize`

The size, in bytes, of an output parameter structure that is described by the <i>SubDeviceID</i> parameter.

`*pOutputParamsBuffer`

A pointer to an output parameter structure that is described by the <i>SubDeviceID</i> parameter.


## Return Value

Returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result.

## Remarks

The Direct3D runtime considers the retrieved subparts to be appended to the Direct3D driver device object and expects  them to be destroyed along with the rest of the device when <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice</a> is called.

Subdevices are retrieved from the root device object independently. The DDI interface version is provided implicitly within the subdevice ID.

This function is free-threaded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs.md">D3DWDDM2_0DDI_VIDEODEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md">D3D11_1DDI_VIDEODEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice</a>