---
UID: NC:d3d10umddi.PFND3D10DDI_SETVIEWPORTS
title: PFND3D10DDI_SETVIEWPORTS
author: windows-driver-content
description: The SetViewports function sets viewports.
old-location: display\setviewports.htm
old-project: display
ms.assetid: f5a55dd3-a8c4-4741-b99e-105021d79603
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _POWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
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
req.alt-api: SetViewports
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
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# PFND3D10DDI_SETVIEWPORTS callback



## -description
The <i>SetViewports</i> function sets viewports.



## -prototype

````
PFND3D10DDI_SETVIEWPORTS SetViewports;

VOID APIENTRY SetViewports(
  _In_       D3D10DDI_HDEVICE   hDevice,
  _In_       UINT               NumViewports,
  _In_       UINT               ClearViewports,
  _In_ const D3D10_DDI_VIEWPORT *pViewports
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param NumViewports [in]

 The total number of viewports that the <i>pViewports</i> parameter specifies. 


### -param ClearViewports [in]

 The number of viewports after the number of viewports that <i>NumViewports </i>specifies to be set to <b>NULL</b>. This number represents the difference between the previous number of viewports (that is, when the Microsoft Direct3D runtime previously called <i>SetViewports</i>) and the new number of viewports. 

Note that the number that <i>ClearViewports</i> specifies is only an optimization aid because the user-mode display driver could calculate this number. 


### -param pViewports [in]

 An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_viewport.md">D3D10_DDI_VIEWPORT</a> structures for the viewports to set. 


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.


## -remarks
Viewports specify the transformation post clip to the output render target and depth stencil resources. Any viewports that are not defined in a call to <i>SetViewports</i> are set to <b>NULL</b>. A <b>NULL</b> viewport is defined as follows. 

This definition implies that the viewport is off.

The user-mode display driver must set all viewports atomically as one operation. 

Although the <i>NumViewports</i> parameter specifies the number of viewports in the array that the <i>pViewports</i> parameter specifies, some values in the array can be <b>NULL</b>. 

The range of viewports between the number that <i>NumViewports</i> specifies and the maximum number of viewports that are allowed is required to contain all <b>NULL</b> or unbound values. The number that the <i>ClearViewports</i> parameter specifies informs the driver about how many viewports the driver must clear out for the current atomic operation. 

If the previous call to <i>SetViewports</i> passed a value of 2 in the <i>NumViewports</i> parameter and the current call to <i>SetViewports</i> passes a value of 4 in <i>NumViewports</i>, the current call to <i>SetViewports</i> also passes a value of 0 in the <i>ClearViewports</i> parameter. If the next successive call to <i>SetViewports</i> passes a value of 1 in <i>NumViewports</i>, the successive call also passes a value of 3 (4 - 1) in <i>ClearViewports</i>.

When the value of clear viewports is requested during user-mode query operations, the value is the difference between the maximum number of viewports and the viewports value.

<i>SetViewports</i> ensures that the viewports are valid. That is, <i>SetViewports</i> ensures that the dimensions of the viewports are within range (D3D10_VIEWPORT_BOUNDS_MIN, D3D10_VIEWPORT_BOUNDS_MAX, D3D10_MIN_DEPTH, and D3D10_MAX_DEPTH). <i>SetViewports</i> also ensures that no coordinates are NaN and flushes denormalized float values to zero.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetViewports</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_viewport.md">D3D10_DDI_VIEWPORT</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETVIEWPORTS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

