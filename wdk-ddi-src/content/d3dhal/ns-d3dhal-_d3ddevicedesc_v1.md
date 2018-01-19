---
UID : NS:d3dhal._D3DDeviceDesc_V1
title : _D3DDeviceDesc_V1
author : windows-driver-content
description : Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DDEVICEDESC_V1 structure describes the 3D capabilities of a device.
old-location : display\d3ddevicedesc_v1.htm
old-project : display
ms.assetid : 363e4044-e835-43e6-96ce-0fdccdd7fb52
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DDeviceDesc_V1, D3DDEVICEDESC_V1, *LPD3DDEVICEDESC_V1
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
req.alt-api : D3DDEVICEDESC_V1
req.alt-loc : d3dhal.h
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
req.typenames : D3DDEVICEDESC_V1, *LPD3DDEVICEDESC_V1
---

# _D3DDeviceDesc_V1 structure
Obsolete in DirectX 8.0 and later versions; see Remarks.
   

The D3DDEVICEDESC_V1 structure describes the 3D capabilities of a device.

## Syntax
````
typedef struct _D3DDeviceDesc_V1 {
  DWORD            dwSize;
  DWORD            dwFlags;
  D3DCOLORMODEL    dcmColorModel;
  DWORD            dwDevCaps;
  D3DTRANSFORMCAPS dtcTransformCaps;
  BOOL             bClipping;
  D3DLIGHTINGCAPS  dlcLightingCaps;
  D3DPRIMCAPS      dpcLineCaps;
  D3DPRIMCAPS      dpcTriCaps;
  DWORD            dwDeviceRenderBitDepth;
  DWORD            dwDeviceZBufferBitDepth;
  DWORD            dwMaxBufferSize;
  DWORD            dwMaxVertexCount;
} D3DDEVICEDESC_V1, *LPD3DDEVICEDESC_V1;
````

## Members

        
            `bClipping`

            Set to <b>TRUE</b> by the driver if the device can perform 3D clipping.
        
            `dcmColorModel`

            Specifies the device's color model.
        
            `dlcLightingCaps`

            Specifies the lighting capabilities of the device. This is a <a href="..\d3dcaps\ns-d3dcaps-_d3dlightingcaps.md">D3DLIGHTINGCAPS</a> structure. The driver must set the <b>dwCaps</b>, <b>dwLightingModel</b>, and <b>dwNumLights</b> members of that structure to zero.
        
            `dpcLineCaps`

            Specifies a <a href="..\d3dcaps\ns-d3dcaps-_d3dprimcaps.md">D3DPRIMCAPS</a> structure that defines the drawing capabilities of the device for line primitives.
        
            `dpcTriCaps`

            Specifies a <a href="..\d3dcaps\ns-d3dcaps-_d3dprimcaps.md">D3DPRIMCAPS</a> structure that defines the drawing capabilities of the device for triangle primitives.
        
            `dtcTransformCaps`

            Specifies a D3DTRANSFORMCAPS structure that specifies the transformation capabilities of the device. The driver must set the <b>dwCaps</b> member of that structure to zero.
        
            `dwDevCaps`

            Identifies the capabilities of the device. This member can be a bitwise OR of any of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDEVCAPS_CANBLTSYSTONONLOCAL

</td>
<td>
The device supports a TexBlt from system memory to sublocal video memory.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_CANRENDERAFTERFLIP

</td>
<td>
The device can queue rendering commands after a page flip. Devices must support this capability on Windows 2000 and later, meaning that the driver would always set this flag.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_DRAWPRIMITIVES2

</td>
<td>
The device can support <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_DRAWPRIMITIVES2EX

</td>
<td>
The device can support Extended <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>; i.e. a DX7-compliant driver.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_DRAWPRIMTLVERTEX

</td>
<td>
The device can draw TLVERTEX primitives. This flag is obsolete but must be set by the driver.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_EXECUTESYSTEMMEMORY

</td>
<td>
The device can use execute buffers from system memory. The driver must always set this bit.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_EXECUTEVIDEOMEMORY

</td>
<td>
The device can use execute buffers from display memory. The driver must never set this bit.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_FLOATTLVERTEX

</td>
<td>
The device accepts floating-point for posttransform vertex data. This flag is obsolete but must be set by the driver.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_HWRASTERIZATION

</td>
<td>
The device has hardware acceleration for rasterization.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_HWTRANSFORMANDLIGHT

</td>
<td>
The device can support transformation and lighting in hardware. D3DDEVCAPS_DRAWPRIMITIVES2EX must also be set.

</td>
</tr>
<tr>
<td>
D3DDEVCAPS_SEPARATETEXTUREMEMORIES

</td>
<td>
        
            `dwDeviceRenderBitDepth`

            Specifies the device's rendering bit-depth. This member can be a bitwise OR of the following DirectDraw bit-depth constants: DDBD_8, DDBD_16, DDBD_24, or DDBD_32.
        
            `dwDeviceZBufferBitDepth`

            Specifies the device's z-buffer bit-depth. This member can be a bitwise OR of the following DirectDraw bit-depth constants: DDBD_8, DDBD_16, DDBD_24, or DDBD_32.
        
            `dwFlags`

            Identifies the members of this structure that contain valid data. This member can be a bitwise OR of any of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDD_BCLIPPING

</td>
<td>
The <b>bClipping</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_COLORMODEL

</td>
<td>
The <b>dcmColorModel</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_DEVCAPS

</td>
<td>
The <b>dwDevCaps</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_DEVICERENDERBITDEPTH

</td>
<td>
The <b>dwDeviceRenderBitDepth</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_DEVICEZBUFFERBITDEPTH

</td>
<td>
The <b>dwDeviceZBufferBitDepth</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_LIGHTINGCAPS

</td>
<td>
The <b>dlcLightingCaps</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_LINECAPS

</td>
<td>
The <b>dpcLineCaps</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_MAXBUFFERSIZE

</td>
<td>
The <b>dwMaxBufferSize</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_MAXVERTEXCOUNT

</td>
<td>
The <b>dwMaxVertexCount</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_TRANSFORMCAPS

</td>
<td>
The <b>dtcTransformCaps</b> member contains valid data.

</td>
</tr>
<tr>
<td>
D3DDD_TRICAPS

</td>
<td>
The <b>dpcTriCaps</b> member contains valid data.

</td>
</tr>
</table>
        
            `dwMaxBufferSize`

            Must be set to zero.
        
            `dwMaxVertexCount`

            
        
            `dwSize`

            Specifies the size in bytes of this D3DDEVICEDESC_V1 structure.

    ## Remarks
        This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for legacy runtime (DirectX 7.0 and earlier) compatibility. See <a href="https://msdn.microsoft.com/a03a7cbc-95be-4251-8e3a-bef4a093f03d">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a> function returns this information in the <a href="..\d3dhal\ns-d3dhal-_d3dhal_globaldriverdata.md">D3DHAL_GLOBALDRIVERDATA</a> structure that the <b>lpD3DGlobalDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a> structure points to.

The Direct3D runtime constructs the application-level D3DDEVICEDESC7 structure (documented in the Microsoft Windows SDK documentation) from the information returned in the D3DDEVICEDESC_V1 structure and the extended capabilities queried through the driver's <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a> function. While some of the <b>dwDevCaps</b> flags are obsolete at the driver level, the driver must set them appropriately in order for applications to work correctly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dcaps\ns-d3dcaps-_d3dlightingcaps.md">D3DLIGHTINGCAPS</a>
</dt>
<dt>
<a href="..\d3dcaps\ns-d3dcaps-_d3dprimcaps.md">D3DPRIMCAPS</a>
</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_globaldriverdata.md">D3DHAL_GLOBALDRIVERDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDEVICEDESC_V1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>