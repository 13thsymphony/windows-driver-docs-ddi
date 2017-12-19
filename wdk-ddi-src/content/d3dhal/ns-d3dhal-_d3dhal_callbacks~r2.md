---
UID: NS.D3DHAL._D3DHAL_CALLBACKS~R2
title: _D3DHAL_CALLBACKS
author: windows-driver-content
description: D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.
old-location: display\d3dhal_callbacks.htm
old-project: display
ms.assetid: 3b045732-a41f-47e7-9835-41e3ef54f14c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DHAL_CALLBACKS, D3DHAL_CALLBACKS, *LPD3DHAL_CALLBACKS
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
---

# _D3DHAL_CALLBACKS structure



## -description
D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.



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

### -field dwSize

Specifies the size in bytes of this D3DHAL_CALLBACKS structure.


### -field ContextCreate

Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextcreatecb.md">D3dContextCreate</a> callback. A driver must implement the callback that this member points to.


### -field ContextDestroy

Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a> callback. A driver must implement the callback that this member points to.


### -field ContextDestroyAll

Must be set to <b>NULL</b> in a Windows 2000 and later driver.


### -field SceneCapture

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dSceneCapture</b> callback. For DirectX 7.0 and later, this callback was replaced by the handling of the D3DRENDERSTATE_SCENECAPTURE render state in the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> function.


### -field lpReserved10

Must be zero.


### -field lpReserved11

Must be zero.


### -field RenderState

Points to the driver-supplied D3DHAL_RENDERSTATEDATA callback. A driver must implement the callback that this member points to.


### -field RenderPrimitive

Points to the driver-supplied D3DHAL_RENDERPRIMITIVEDATA callback. A driver must implement the callback that this member points to.


### -field dwReserved

Specifies reserved fields and must be set to zero.


### -field TextureCreate

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureCreate</b> callback, or <b>NULL</b>. 


### -field TextureDestroy

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureDestroy</b> callback, or <b>NULL</b>.


### -field TextureSwap

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureSwap</b> callback, or <b>NULL</b>.


### -field TextureGetSurf

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureGetSurf</b> callback, or <b>NULL</b>.


### -field lpReserved12

Must be zero.


### -field lpReserved13

Must be zero.


### -field lpReserved14

Must be zero.


### -field lpReserved15

Must be zero.


### -field lpReserved16

Must be zero.


### -field lpReserved17

Must be zero.


### -field lpReserved18

Must be zero.


### -field lpReserved19

Must be zero.


### -field lpReserved20

Must be zero.


### -field lpReserved21

Must be zero.


### -field GetState

Points to the driver-supplied D3DHAL_GETSTATEDATA callback. A driver must implement the callback that this member points to.


### -field dwReserved0

Must be zero.


### -field dwReserved1

Must be zero.


### -field dwReserved2

Must be zero.


### -field dwReserved3

Must be zero.


### -field dwReserved4

Must be zero.


### -field dwReserved5

Must be zero.


### -field dwReserved6

Must be zero.


### -field dwReserved7

Must be zero.


### -field dwReserved8

Must be zero


### -field dwReserved9

Must be zero.


## -remarks
The driver allocates this structure and sets appropriate values in all members. The driver's <a href="display.drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a> function returns a pointer to this structure in the <b>lpD3DHALCallbacks</b> member of the <a href="display.dd_halinfo">DD_HALINFO</a> structure.

Texture management is now handled though opcodes that are managed in the driver's implementation of <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextcreatecb.md">D3dContextCreate</a>
</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a>
</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="display.d3dhal_callbacks3">D3DHAL_CALLBACKS3</a>
</dt>
<dt>
<a href="display.ddgetdriverinfo">DdGetDriverInfo</a>
</dt>
<dt>
<a href="display.drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_CALLBACKS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

