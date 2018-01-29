---
UID : NS:d3dhal._D3DHAL_CALLBACKS
title : _D3DHAL_CALLBACKS
author : windows-driver-content
description : D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.
old-location : display\d3dhal_callbacks.htm
old-project : display
ms.assetid : 3b045732-a41f-47e7-9835-41e3ef54f14c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dhal/LPD3DHAL_CALLBACKS, LPD3DHAL_CALLBACKS structure pointer [Display Devices], *LPD3DHAL_CALLBACKS, LPD3DHAL_CALLBACKS, d3dstrct_2dc02d2c-6ae9-4f2e-9cb3-470926980537.xml, _D3DHAL_CALLBACKS, display.d3dhal_callbacks, D3DHAL_CALLBACKS, D3DHAL_CALLBACKS structure [Display Devices], d3dhal/D3DHAL_CALLBACKS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dhal.h
req.include-header : D3dhal.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DHAL_CALLBACKS, *LPD3DHAL_CALLBACKS
---

# _D3DHAL_CALLBACKS structure
D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.

## Syntax
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

## Members


`ContextCreate`

Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextcreatecb.md">D3dContextCreate</a> callback. A driver must implement the callback that this member points to.

`ContextDestroy`

Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a> callback. A driver must implement the callback that this member points to.

`ContextDestroyAll`

Must be set to <b>NULL</b> in a Windows 2000 and later driver.

`dwReserved`

Specifies reserved fields and must be set to zero.

`dwReserved0`

Must be zero.

`dwReserved1`

Must be zero.

`dwReserved2`

Must be zero.

`dwReserved3`

Must be zero.

`dwReserved4`

Must be zero.

`dwReserved5`

Must be zero.

`dwReserved6`

Must be zero.

`dwReserved7`

Must be zero.

`dwReserved8`

Must be zero

`dwReserved9`

Must be zero.

`dwSize`

Specifies the size in bytes of this D3DHAL_CALLBACKS structure.

`GetState`

Points to the driver-supplied D3DHAL_GETSTATEDATA callback. A driver must implement the callback that this member points to.

`lpReserved10`

Must be zero.

`lpReserved11`

Must be zero.

`lpReserved12`

Must be zero.

`lpReserved13`

Must be zero.

`lpReserved14`

Must be zero.

`lpReserved15`

Must be zero.

`lpReserved16`

Must be zero.

`lpReserved17`

Must be zero.

`lpReserved18`

Must be zero.

`lpReserved19`

Must be zero.

`lpReserved20`

Must be zero.

`lpReserved21`

Must be zero.

`RenderPrimitive`

Points to the driver-supplied D3DHAL_RENDERPRIMITIVEDATA callback. A driver must implement the callback that this member points to.

`RenderState`

Points to the driver-supplied D3DHAL_RENDERSTATEDATA callback. A driver must implement the callback that this member points to.

`SceneCapture`

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dSceneCapture</b> callback. For DirectX 7.0 and later, this callback was replaced by the handling of the D3DRENDERSTATE_SCENECAPTURE render state in the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> function.

`TextureCreate`

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureCreate</b> callback, or <b>NULL</b>.

`TextureDestroy`

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureDestroy</b> callback, or <b>NULL</b>.

`TextureGetSurf`

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureGetSurf</b> callback, or <b>NULL</b>.

`TextureSwap`

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureSwap</b> callback, or <b>NULL</b>.

## Remarks
The driver allocates this structure and sets appropriate values in all members. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a> function returns a pointer to this structure in the <b>lpD3DHALCallbacks</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a> structure.

Texture management is now handled though opcodes that are managed in the driver's implementation of <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a>

<a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_callbacks3.md">D3DHAL_CALLBACKS3</a>

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextcreatecb.md">D3dContextCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_CALLBACKS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>