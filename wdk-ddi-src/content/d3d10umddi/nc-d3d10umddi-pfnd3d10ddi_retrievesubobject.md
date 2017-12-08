---
UID: NC.d3d10umddi.PFND3D10DDI_RETRIEVESUBOBJECT
title: PFND3D10DDI_RETRIEVESUBOBJECT
author: windows-driver-content
description: Retrieves subparts of the Microsoft Direct3D driver device object.
old-location: display\retrievesubobject_d3d11_1_.htm
old-project: display
ms.assetid: 9029ec8d-102f-4d83-8ab5-fc208d8b5249
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
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
req.alt-api: RetrieveSubObject(D3D11_1)
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
---

# PFND3D10DDI_RETRIEVESUBOBJECT callback



## -description
Retrieves subparts of the Microsoft Direct3D driver device object. 


## -prototype

````
PFND3D10DDI_RETRIEVESUBOBJECT RetrieveSubObject(D3D11_1);

HRESULT APIENTRY* RetrieveSubObject(D3D11_1)(
        D3D10DDI_HDEVICE hDevice,
  _In_  UINT32           SubDeviceID,
  _In_  SIZE_T           ParamSize,
  _In_  void             *pParams,
  _In_  SIZE_T           OutputParamSize,
  _Out_ void             *pOutputParamsBuffer
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).



### -param SubDeviceID [in]

The function table being retrieved, with the following possible values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -param 1

</td>
<td width="60%">
A video function table that is described as a   structure. The function returns a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md">D3D11_1DDI_VIDEODEVICEFUNCS</a> structure in the buffer referenced by the <i>pOutputParamsBuffer</i> parameter.
</td>
</tr>
<tr>
<td width="40%">

### -param 3

</td>
<td width="60%">
A WDDM 2.0 and later video function table that is described as a   structure. The function returns a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs.md">D3DWDDM2_0DDI_VIDEODEVICEFUNCS</a> structure in the buffer referenced by the <i>pOutputParamsBuffer</i> parameter.
Supported starting with WDDM 2.0.
</td>
</tr>
</table>
 

### -param ParamSize [in]

The size, in bytes, of an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param pParams [in]

A pointer to an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param OutputParamSize [in]

The size, in bytes, of an output parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param pOutputParamsBuffer [out]

A pointer to an output parameter structure that is described by the <i>SubDeviceID</i> parameter.

## -returns
Returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. 


## -remarks
The Direct3D runtime considers the retrieved subparts to be appended to the Direct3D driver device object and expects  them to be destroyed along with the rest of the device when <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice</a> is called.

Subdevices are retrieved from the root device object independently. The DDI interface version is provided implicitly within the subdevice ID.

This function is free-threaded.

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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md">D3D11_1DDI_VIDEODEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs.md">D3DWDDM2_0DDI_VIDEODEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RETRIEVESUBOBJECT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
