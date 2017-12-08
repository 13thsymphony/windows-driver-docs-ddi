---
UID: NC.d3d10umddi.PFND3D10DDI_SETERROR_CB
title: PFND3D10DDI_SETERROR_CB
author: windows-driver-content
description: The pfnSetErrorCb function sets the return error code of a user-mode display driver's function.
old-location: display\pfnseterrorcb.htm
old-project: display
ms.assetid: 968b04a7-8869-410c-a6fc-83d57726858f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
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
req.alt-api: pfnSetErrorCb
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

# PFND3D10DDI_SETERROR_CB callback



## -description
The <b>pfnSetErrorCb</b> function sets the return error code of a user-mode display driver's function.


## -prototype

````
PFND3D10DDI_SETERROR_CB pfnSetErrorCb;

void APIENTRY pfnSetErrorCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice,
  _In_ HRESULT               hResult
)
{ ... }
````


## -parameters

### -param hRuntimeDevice [in]

 A handle to a context for the core Microsoft Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 

### -param hResult [in]

 An HRESULT value that specifies the error to set for a driver function. 

## -returns
None

## -remarks
A user-mode display driver can call <b>pfnSetErrorCb</b> many times for each driver invocation. For the driver's functions that do not return status codes, the driver uses <b>pfnSetErrorCb</b> to return error information to the Direct3D runtime. 

## -requirements
<table>
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
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETERROR_CB callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
