---
UID: NS.d3dhal._D3DHAL_CALLBACKS~r2
title: D3DHAL_CALLBACKS
author: windows-driver-content
description: D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.
old-location: display\d3dhal_callbacks.htm
old-project: display
ms.assetid: 3b045732-a41f-47e7-9835-41e3ef54f14c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_CALLBACKS, D3DHAL_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_CALLBACKS
req.alt-loc: d3dhal.h
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

# D3DHAL_CALLBACKS structure



## -description
<p>D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.</p>


## -syntax

````
typedef struct _D3DHAL_CALLBACKS {
  DWORD                        dwSize;
  LPD3DHAL_CONTEXTCREATECB     ContextCreate;
  LPD3DHAL_CONTEXTDESTROYCB    ContextDestroy;
  LPD3DHAL_CONTEXTDESTROYALLCB ContextDestroyAll;
  LPD3DHAL_SCENECAPTURECB      SceneCapture;
  LPVOID                       lpReserved10;
  LPVOID                       lpReserved11;
  LPD3DHAL_RENDERSTATECB       RenderState;
  LPD3DHAL_RENDERPRIMITIVECB   RenderPrimitive;
  DWORD                        dwReserved;
  LPD3DHAL_TEXTURECREATECB     TextureCreate;
  LPD3DHAL_TEXTUREDESTROYCB    TextureDestroy;
  LPD3DHAL_TEXTURESWAPCB       TextureSwap;
  LPD3DHAL_TEXTUREGETSURFCB    TextureGetSurf;
  LPVOID                       lpReserved12;
  LPVOID                       lpReserved13;
  LPVOID                       lpReserved14;
  LPVOID                       lpReserved15;
  LPVOID                       lpReserved16;
  LPVOID                       lpReserved17;
  LPVOID                       lpReserved18;
  LPVOID                       lpReserved19;
  LPVOID                       lpReserved20;
  LPVOID                       lpReserved21;
  LPD3DHAL_GETSTATECB          GetState;
  DWORD                        dwReserved0;
  DWORD                        dwReserved1;
  DWORD                        dwReserved2;
  DWORD                        dwReserved3;
  DWORD                        dwReserved4;
  DWORD                        dwReserved5;
  DWORD                        dwReserved6;
  DWORD                        dwReserved7;
  DWORD                        dwReserved8;
  DWORD                        dwReserved9;
} D3DHAL_CALLBACKS, *LPD3DHAL_CALLBACKS;
````


## -struct-fields
<dl>

### -field dwSize

<dd>
<p>Specifies the size in bytes of this D3DHAL_CALLBACKS structure.</p>
</dd>

### -field ContextCreate

<dd>
<p>Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextcreatecb.md">D3dContextCreate</a> callback. A driver must implement the callback that this member points to.</p>
</dd>

### -field ContextDestroy

<dd>
<p>Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextdestroycb.md">D3dContextDestroy</a> callback. A driver must implement the callback that this member points to.</p>
</dd>

### -field ContextDestroyAll

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver.</p>
</dd>

### -field SceneCapture

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dSceneCapture</b> callback. For DirectX 7.0 and later, this callback was replaced by the handling of the D3DRENDERSTATE_SCENECAPTURE render state in the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> function.</p>
</dd>

### -field lpReserved10

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved11

<dd>
<p>Must be zero.</p>
</dd>

### -field RenderState

<dd>
<p>Points to the driver-supplied D3DHAL_RENDERSTATEDATA callback. A driver must implement the callback that this member points to.</p>
</dd>

### -field RenderPrimitive

<dd>
<p>Points to the driver-supplied D3DHAL_RENDERPRIMITIVEDATA callback. A driver must implement the callback that this member points to.</p>
</dd>

### -field dwReserved

<dd>
<p>Specifies reserved fields and must be set to zero.</p>
</dd>

### -field TextureCreate

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureCreate</b> callback, or <b>NULL</b>. </p>
</dd>

### -field TextureDestroy

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureDestroy</b> callback, or <b>NULL</b>.</p>
</dd>

### -field TextureSwap

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureSwap</b> callback, or <b>NULL</b>.</p>
</dd>

### -field TextureGetSurf

<dd>
<p>Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureGetSurf</b> callback, or <b>NULL</b>.</p>
</dd>

### -field lpReserved12

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved13

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved14

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved15

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved16

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved17

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved18

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved19

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved20

<dd>
<p>Must be zero.</p>
</dd>

### -field lpReserved21

<dd>
<p>Must be zero.</p>
</dd>

### -field GetState

<dd>
<p>Points to the driver-supplied D3DHAL_GETSTATEDATA callback. A driver must implement the callback that this member points to.</p>
</dd>

### -field dwReserved0

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved1

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved2

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved3

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved4

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved5

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved6

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved7

<dd>
<p>Must be zero.</p>
</dd>

### -field dwReserved8

<dd>
<p>Must be zero</p>
</dd>

### -field dwReserved9

<dd>
<p>Must be zero.</p>
</dd>
</dl>

## -remarks
<p>The driver allocates this structure and sets appropriate values in all members. The driver's <a href="display.drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a> function returns a pointer to this structure in the <b>lpD3DHALCallbacks</b> member of the <a href="display.dd_halinfo">DD_HALINFO</a> structure.</p>

<p>Texture management is now handled though opcodes that are managed in the driver's implementation of <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextcreatecb.md">D3dContextCreate</a>
</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextdestroycb.md">D3dContextDestroy</a>
</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-callbacks3.md">D3DHAL_CALLBACKS3</a>
</dt>
<dt>
<a href="display.ddgetdriverinfo">DdGetDriverInfo</a>
</dt>
<dt>
<a href="display.drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_CALLBACKS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
