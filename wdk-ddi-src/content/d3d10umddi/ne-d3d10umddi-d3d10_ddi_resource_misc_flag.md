---
UID: NE:d3d10umddi.D3D10_DDI_RESOURCE_MISC_FLAG
title: D3D10_DDI_RESOURCE_MISC_FLAG
author: windows-driver-content
description: Identifies miscellaneous information about a resource.
old-location: display\d3d10_ddi_resource_misc_flag.htm
old-project: display
ms.assetid: 1de11acf-1571-44ae-9bde-2b417bf615b7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D10_DDI_RESOURCE_MISC_FLAG, d3d10umddi/D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP, D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER, D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS, d3d10umddi/, d3d10umddi/D3D10_DDI_RESOURCE_MISC_SHARED, d3d10umddi/D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS, D3DWDDM1_3DDI_RESOURCE_MISC_TILED, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL, D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED, D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED, D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP, D3D10_DDI_RESOURCE_MISC_FLAG enumeration [Display Devices], d3d10umddi/D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_TILED, D3D10_DDI_RESOURCE_MISC_SHARED, d3d10umddi/D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER, D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED, d3d10umddi/D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP, D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED, D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE, d3d10umddi/D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT, d3d10umddi/D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS, D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS, d3d10umddi/D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED, D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT, d3d10umddi/D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT, d3d10umddi/D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE, UMDisplayDriver_Dx10param_Structs_0b144bfc-1cec-4e30-b7c6-f7c2cb7d4567.xml, D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT, d3d10umddi/D3D10_DDI_RESOURCE_MISC_REMOTE, D3D10_DDI_RESOURCE_MISC_REMOTE, d3d10umddi/D3D10_DDI_RESOURCE_MISC_FLAG, D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP, D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL, display.d3d10_ddi_resource_misc_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_RESOURCE_MISC_FLAG
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RESOURCE_MISC_FLAG
---

# D3D10_DDI_RESOURCE_MISC_FLAG Enumeration
Identifies miscellaneous information about a resource.

## Syntax
````
typedef enum D3D10_DDI_RESOURCE_MISC_FLAG { 
  D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP                       = 0x00000001L,
  D3D10_DDI_RESOURCE_MISC_SHARED                            = 0x00000002L,
  D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT                = 0x00000008L,
#if D3D11DDI_MINOR_HEADER_VERSION >= 1
  D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS                 = 0x00000010L,
  D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS            = 0x00000020L,
  D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED                 = 0x00000040L,
  D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP                    = 0x00000080L,
#endif 
  D3D10_DDI_RESOURCE_MISC_REMOTE                            = 0x00000400L,
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT               = 0x00000800L,
  D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER  = 0x00001000L,
#endif 
#if D3D11DDI_MINOR_HEADER_VERSION >= 4
  D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER                 = 0x00002000L,
  D3DWDDM1_3DDI_RESOURCE_MISC_TILED                         = 0x00004000L,
  D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL                     = 0x00008000L,
#endif 
#if D3D11DDI_MINOR_HEADER_VERSION >= 5
  D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED                  = 0x00010000L,
  D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE           = 0x00020000L,
  D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED         = 0x00040000L,
#endif 
  
} D3D10_DDI_RESOURCE_MISC_FLAG;
````

## Constants

<table>
            
                <tr>
                    <td>D3D10_DDI_RESOURCE_AUTO_GEN_MIP_MAP</td>
                    <td>The resource can be used with the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_genmips.md">GenMips</a> function.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT</td>
                    <td>The resource is not required to persist across presentations. 
      

For more information about this value, see the Remarks section of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> reference page.

Supported starting with Windows Server 2008, and Windows Vista with Service Pack 1 (SP1).</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_RESOURCE_MISC_REMOTE</td>
                    <td>This value is for internal use only. Do not use.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_RESOURCE_MISC_SHARED</td>
                    <td>The resource can be shared by multiple devices and processes.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_RESOURCE_MISC_RESTRICT_SHARED_RESOURCE_DRIVER</td>
                    <td>The driver should restrict access to the shared surface. This value should be used only when a shared surface is created. The process that is creating the surface is always allowed to open the shared resource.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_RESOURCE_MISC_RESTRICTED_CONTENT</td>
                    <td>The resource can contain protected content. This value should be used only if the driver and hardware support content protection.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_RESOURCE_MISC_BUFFER_ALLOW_RAW_VIEWS</td>
                    <td>The resource is a buffer on which the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a> function can create a raw-format view. A raw-format view is created through a call to the driver's <b>CreateShaderResourceView(D3D11)</b> function with the D3D11_DDI_BUFFEREX_SRV_FLAG_RAW flag set in the <b>BufferEx</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure. Raw-format views allow to read (and write in the case of unordered access view (UAV) objects) up to four DWORD values in one instruction.

Supported starting with Windows 7.

Supported in Windows 7 and later versions.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_RESOURCE_MISC_BUFFER_STRUCTURED</td>
                    <td>The resource is a buffer that has its memory sectioned into equally sized pieces (structures). The structure size of each piece is provided in the resource declaration. The drivers might be able to use this information to optimize memory layout.

Supported starting with Windows 7.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS</td>
                    <td>The resource is a buffer that the runtime can use as the argument buffer in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect.md">DrawIndexedInstancedIndirect</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect.md">DrawInstancedIndirect</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatchindirect.md">DispatchIndirect</a> function.

Supported starting with Windows 7.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_RESOURCE_MISC_RESOURCE_CLAMP</td>
                    <td>The resource must consider any resource clamp, which a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md">SetResourceMinLOD</a> function applies.

Supported starting with Windows 7.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDI_RESOURCE_MISC_CROSS_ADAPTER</td>
                    <td>The resource is a shared cross-adapter resource.

The user-mode display driver should record information about the cross-adapter resource in a private driver data structure. The display miniport driver can call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function  to retrieve this private data.

The DirectX graphics kernel subsystem calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_describeallocation.md">DxgkDdiDescribeAllocation</a> function to get information on the cross-adapter resource when it needs to open the resource on another adapter. The display miniport must ensure that this information is correct.

Supported starting with Windows 8.1.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDI_RESOURCE_MISC_TILE_POOL</td>
                    <td>The resource is a tile pool.  Must be a buffer with <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a> usage type <b>D3D10_DDI_USAGE_DEFAULT</b>.

Supported starting with Windows 8.1.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDI_RESOURCE_MISC_TILED</td>
                    <td>The resource is tiled. 

Supported starting with Windows 8.1.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_RESOURCE_MISC_CONTAINS_HW_PROTECTED</td>
                    <td>The decoder input buffer contains encrypted protected content. The hardware does not need to protect these buffers (as they are encrypted), but the driver may need to allocate these buffers differently so they can efficiently interact with their decryption hardware.

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE</td>
                    <td>The resource contains a displayable surface.

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_RESOURCE_MISC_HW_PROTECTED</td>
                    <td>The resource should be created such that it will be protected by the hardware. 

Supported starting with Windows 10.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md">SetResourceMinLOD</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect.md">DrawInstancedIndirect</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatchindirect.md">DispatchIndirect</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md">SetResourceMinLOD</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect.md">DrawIndexedInstancedIndirect</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_genmips.md">GenMips</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_RESOURCE_MISC_FLAG enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>