---
UID: NC.d3d10umddi.PFND3D11_1DDI_CHECKVIDEODECODERFORMAT
title: PFND3D11_1DDI_CHECKVIDEODECODERFORMAT
author: windows-driver-content
description: Determines whether a specified format can be used as a video decoder output format for a specified DirectX Video Acceleration (DXVA) profile.
old-location: display\checkvideodecoderformat.htm
old-project: display
ms.assetid: 6bde6e00-70ba-4fa5-9cc0-9884ce7381ed
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: CheckVideoDecoderFormat
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_CHECKVIDEODECODERFORMAT callback



## -description
Determines whether a specified format can be used as a video decoder output format for a specified DirectX Video Acceleration (DXVA) profile.



## -prototype

````
PFND3D11_1DDI_CHECKVIDEODECODERFORMAT CheckVideoDecoderFormat;

VOID APIENTRY* CheckVideoDecoderFormat(
  _In_        D3D10DDI_HDEVICE hDevice,
  _In_  const GUID             *pDecoderProfile ,
  _In_        DXGI_FORMAT      Format,
  _Out_       BOOL             *pBool
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pDecoderProfile  [in]

A pointer to a GUID that identifies the DXVA profile. 


### -param Format [in]

A DXGI_FORMAT value that specifies the output format. Typical values include DXGI_FORMAT_NV12 and DXGI_FORMAT_420_OPAQUE.


### -param pBool [out]

A BOOL value that, if TRUE, specifies that the specified format can be used  for the specified DXVA profile.


## -returns
This callback function does not return a value.


## -remarks
This function is not expected to fail.


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