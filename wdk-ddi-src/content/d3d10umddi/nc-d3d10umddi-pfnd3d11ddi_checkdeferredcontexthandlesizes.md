---
UID: NC.d3d10umddi.PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES
title: PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES
author: windows-driver-content
description: The CheckDeferredContextHandleSizes function verifies the sizes of the driver-private memory spaces that hold the handle data of deferred context handles.
old-location: display\checkdeferredcontexthandlesizes.htm
old-project: display
ms.assetid: 0ddaec86-79e6-4d09-8403-6588b35f8b0f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CheckDeferredContextHandleSizes is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CheckDeferredContextHandleSizes
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

# PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES callback



## -description
The <b>CheckDeferredContextHandleSizes</b> function verifies the sizes of the driver-private memory spaces that hold the handle data of deferred context handles.



## -prototype

````
PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES CheckDeferredContextHandleSizes;

VOID APIENTRY CheckDeferredContextHandleSizes(
  _In_      D3D10DDI_HDEVICE    hDevice,
  _Inout_   UINT                *pHSizes,
  _Out_opt_ D3D11DDI_HANDLESIZE *pHandleSize
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pHSizes [in, out]

The size, in bytes, of the array pointed to by <i>pHandleSize</i>.


### -param pHandleSize [out, optional]

 An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_handlesize.md">D3D11DDI_HANDLESIZE</a> structures that describe the handle data of deferred context handles.


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set a critical error code. For more information about setting error codes, see the Remarks section.


## -remarks
The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the <b>D3D11DDICAPS_COMMANDLISTS_BUILD_2</b> capability that can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

For more information about how <i>CheckDeferredContextHandleSizes</i> is used, see <a href="https://msdn.microsoft.com/1b3e5c29-9b9e-4c10-8fe0-706255c8fd91">Using Context-Local DDI Handles</a>. 

The driver's <i>CheckDeferredContextHandleSizes</i> function cannot call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code because <i>CheckDeferredContextHandleSizes</i> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <i>CheckDeferredContextHandleSizes</i>, even in the presence of <b>D3DDDIERR_DEVICEREMOVED</b>.

<i>CheckDeferredContextHandleSizes</i> should not encounter any errors. However, <i>CheckDeferredContextHandleSizes</i> might call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> for critical errors.


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
<i>CheckDeferredContextHandleSizes</i> is supported beginning with the Windows 7 operating system. 

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md">CheckDeferredContextHandleSizes</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs~r1.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

