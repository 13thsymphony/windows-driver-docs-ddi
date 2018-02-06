---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
title: "_D3DKMDT_VIDPN_PRESENT_PATH_ROTATION"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration is used to indicate the rotation angle applied to content displayed on a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_rotation.htm
old-project: display
ms.assetid: 4966ba24-35ed-453a-9483-bd3337e31b83
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMDT_VPPR_ROTATE180, d3dkmdt/D3DKMDT_VPPR_ROTATE270_OFFSET270, d3dkmdt/D3DKMDT_VPPR_ROTATE270_OFFSET90, D3DKMDT_VPPR_ROTATE90_OFFSET90, D3DKMDT_VPPR_IDENTITY, d3dkmdt/D3DKMDT_VPPR_ROTATE90_OFFSET90, d3dkmdt/D3DKMDT_VPPR_IDENTITY_OFFSET270, D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration [Display Devices], d3dkmdt/D3DKMDT_VPPR_UNPINNED, D3DKMDT_VPPR_ROTATE270_OFFSET90, D3DKMDT_VPPR_IDENTITY_OFFSET180, D3DKMDT_VPPR_ROTATE270, d3dkmdt/D3DKMDT_VPPR_ROTATE180_OFFSET270, d3dkmdt/D3DKMDT_VPPR_ROTATE90_OFFSET180, d3dkmdt/D3DKMDT_VPPR_IDENTITY, display.d3dkmdt_vidpn_present_path_rotation, D3DKMDT_VPPR_ROTATE180_OFFSET90, d3dkmdt/D3DKMDT_VPPR_ROTATE180_OFFSET180, d3dkmdt/D3DKMDT_VPPR_ROTATE270_OFFSET180, D3DKMDT_VPPR_UNPINNED, D3DKMDT_VPPR_ROTATE180_OFFSET180, D3DKMDT_VPPR_ROTATE90_OFFSET270, d3dkmdt/D3DKMDT_VPPR_ROTATE180_OFFSET90, d3dkmdt/D3DKMDT_VPPR_UNINITIALIZED, d3dkmdt/D3DKMDT_VPPR_ROTATE270, _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION, D3DKMDT_VPPR_IDENTITY_OFFSET90, d3dkmdt/D3DKMDT_VPPR_ROTATE90, d3dkmdt/D3DKMDT_VPPR_ROTATE90_OFFSET270, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_ROTATION, D3DKMDT_VPPR_ROTATE270_OFFSET270, d3dkmdt/D3DKMDT_VPPR_NOTSPECIFIED, D3DKMDT_VPPR_NOTSPECIFIED, D3DKMDT_VPPR_IDENTITY_OFFSET270, d3dkmdt/D3DKMDT_VPPR_IDENTITY_OFFSET90, D3DKMDT_VIDPN_PRESENT_PATH_ROTATION, DmEnums_f69499aa-0366-4826-ada7-0c3107842fc8.xml, d3dkmdt/D3DKMDT_VPPR_ROTATE180, D3DKMDT_VPPR_UNINITIALIZED, D3DKMDT_VPPR_ROTATE90_OFFSET180, D3DKMDT_VPPR_ROTATE270_OFFSET180, D3DKMDT_VPPR_ROTATE90, d3dkmdt/D3DKMDT_VPPR_IDENTITY_OFFSET180, D3DKMDT_VPPR_ROTATE180_OFFSET270
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION Enumeration
The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration is used to indicate the rotation angle applied to content displayed on a VidPN present path.

## Syntax
````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION { 
  D3DKMDT_VPPR_UNINITIALIZED        = 0,
  D3DKMDT_VPPR_IDENTITY             = 1,
  D3DKMDT_VPPR_ROTATE90             = 2,
  D3DKMDT_VPPR_ROTATE180            = 3,
  D3DKMDT_VPPR_ROTATE270            = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION)
  D3DKMDT_VPPR_IDENTITY_OFFSET90    = 5,
  D3DKMDT_VPPR_ROTATE90_OFFSET90    = 6,
  D3DKMDT_VPPR_ROTATE180_OFFSET90   = 7,
  D3DKMDT_VPPR_ROTATE270_OFFSET90   = 8,
  D3DKMDT_VPPR_IDENTITY_OFFSET180   = 9,
  D3DKMDT_VPPR_ROTATE90_OFFSET180   = 10,
  D3DKMDT_VPPR_ROTATE180_OFFSET180  = 11,
  D3DKMDT_VPPR_ROTATE270_OFFSET180  = 12,
  D3DKMDT_VPPR_IDENTITY_OFFSET270   = 13,
  D3DKMDT_VPPR_ROTATE90_OFFSET270   = 14,
  D3DKMDT_VPPR_ROTATE180_OFFSET270  = 15,
  D3DKMDT_VPPR_ROTATE270_OFFSET270  = 16,
#endif 
  D3DKMDT_VPPR_UNPINNED             = 254,
  D3DKMDT_VPPR_NOTSPECIFIED         = 255
} D3DKMDT_VIDPN_PRESENT_PATH_ROTATION;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMDT_VPPR_IDENTITY</td>
                    <td>Indicates that there is no rotation.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_IDENTITY_OFFSET180</td>
                    <td>Indicates that source content is not modified in any way, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_IDENTITY_OFFSET270</td>
                    <td>Indicates that source content is not modified in any way, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_IDENTITY_OFFSET90</td>
                    <td>Indicates that source content is not modified in any way, and the display miniport driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_NOTSPECIFIED</td>
                    <td>Indicates that no rotation angle (including identity) has been specified.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE180</td>
                    <td>Indicates that the rotation angle is 180 degrees counter-clockwise.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE180_OFFSET180</td>
                    <td>Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE180_OFFSET270</td>
                    <td>Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE180_OFFSET90</td>
                    <td>Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE270</td>
                    <td>Indicates that the rotation angle is 270 degrees counter-clockwise.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE270_OFFSET180</td>
                    <td>Indicates that source content is rotated 270 degrees, and the driver should rotate this content an extra 180 degrees. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE270_OFFSET270</td>
                    <td>Indicates that source content is rotated 270 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE270_OFFSET90</td>
                    <td>Indicates that source content is rotated 270 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE90</td>
                    <td>Indicates that the rotation angle is 90 degrees counter-clockwise.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE90_OFFSET180</td>
                    <td>Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE90_OFFSET270</td>
                    <td>Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_ROTATE90_OFFSET90</td>
                    <td>Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_UNINITIALIZED</td>
                    <td>Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_ROTATION has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPR_UNPINNED</td>
                    <td>Indicates that no rotation angle has been pinned for the VidPN present path.</td>
                </tr>
</table>

    ## Remarks

        The <b>Rotation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure is a value from the <b>D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</b> enumeration.

Starting with Windows 8.1 Update, new constant values (<b>D3DKMDT_VPPR_XXX_OFFSETXXX</b>) are available to specify both the default orientation of a display device and an additional angle (offset) that the user has rotated the device.

Here are some examples of how to set the default orientation and offset:
<ul>
<li>If the  topology is specified as:<ul>
<li>a single monitor,</li>
<li>a non-path-independent rotation clone, or</li>
<li>a primary monitor for a path-independent rotation clone,</li>
</ul> use one of the enumeration values 1 through 4:<ul>
<li><b>D3DKMDT_VPPR_IDENTITY</b></li>
<li><b>D3DKMDT_VPPR_ROTATE90</b></li>
<li><b>D3DKMDT_VPPR_ROTATE180</b></li>
<li><b>D3DKMDT_VPPR_ROTATE270</b></li>
</ul>
</li>
<li>For a path-independent rotation clone, the secondary monitor probably has <b>D3DKMDT_VPPR_XXX_OFFSET270</b> set if it is a portrait-first panel.</li>
<li>Also consider these uncommon scenarios:<ul>
<li>For a path-independent rotation clone, a landscape-first display panel connected to a portrait-first primary device will probably have <b>D3DKMDT_VPPR_XXX_OFFSET90</b> set.</li>
<li>For a path-independent rotation clone on a system prior to Windows 8.1, a landscape-first display panel connected to a landscape-first primary device will probably have <b>D3DKMDT_VPPR_XXX_OFFSET180</b> set.</li>
</ul>
</li>
</ul><div class="alert"><b>Note</b>  The operating system does not update the value of the interface version value <b>DXGKDDI_INTERFACE_VERSION</b> to  <b>DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION</b>. If you want to use the path-independent members in this structure, you should be sure that the interface version in your driver is &gt;= <b>DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION</b> (0x4003).</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>