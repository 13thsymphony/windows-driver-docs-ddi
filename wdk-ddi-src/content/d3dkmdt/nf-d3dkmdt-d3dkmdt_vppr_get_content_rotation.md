---
UID: NF.d3dkmdt.D3DKMDT_VPPR_GET_CONTENT_ROTATION
title: D3DKMDT_VPPR_GET_CONTENT_ROTATION function
author: windows-driver-content
description: A helper function that extracts the combined rotation that the user sees from the default display orientation from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration.
old-location: display\d3dkmdt_vppr_get_content_rotation.htm
old-project: display
ms.assetid: 61C1EB2F-E4CF-4B18-AD7B-6B24EF14E71F
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DKMDT_VPPR_GET_CONTENT_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VPPR_GET_CONTENT_ROTATION
req.alt-loc: D3dkmdt.h
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

# D3DKMDT_VPPR_GET_CONTENT_ROTATION function



## -description
A helper function that extracts the combined rotation that the user sees from the default display orientation from a given value of the <a href="display.d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration. This value is effectively the sum of the offset angle and the angle that the Desktop Window Manager (DWM) has already rotated the primary clone path content. Only drivers that support path-independent rotation (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION) should call this function.



## -syntax

````
__inline
D3DKMDT_VIDPN_PRESENT_PATH_ROTATION D3DKMDT_VPPR_GET_CONTENT_ROTATION(
   D3DKMDT_VIDPN_PRESENT_PATH_ROTATION Rotation
);
````


## -parameters

### -param Rotation 

On input, a value from  the <a href="display.d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration.

On output, a value between 1 and 4, inclusive, that corresponds to the <b>OFFSET</b> portion of the <a href="display.d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> constant values. An output value of 1 (identity) represents 0 degrees of total rotation, 2 represents 90 degrees, and so on. An output value of 0 indicates that the VidPN path is not initialized.

The output value of <i>Rotation</i> is the sum of the output values from the <a href="display.d3dkmdt_vppr_get_content_rotation_part">D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART</a> and <a href="display.d3dkmdt_vppr_get_offset_rotation">D3DKMDT_VPPR_GET_OFFSET_ROTATION</a> functions minus 1.


## -returns
The returned value corresponds to the rotation and offset angles as follows:<table>
<tr>
<td>Input enumeration value</td>
<td>Input enumeration constant</td>
<td>Rotation + offset, in degrees</td>
<td>Output <i>Rotation</i> value</td>
</tr>
<tr>
<td>0</td>
<td><b>D3DKMDT_VPPR_UNINITIALIZED</b></td>
<td>-</td>
<td>0</td>
</tr>
<tr>
<td>1</td>
<td><b>D3DKMDT_VPPR_IDENTITY</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>2</td>
<td><b>D3DKMDT_VPPR_ROTATE90</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>3</td>
<td><b>D3DKMDT_VPPR_ROTATE180</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>4</td>
<td><b>D3DKMDT_VPPR_ROTATE270</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>5</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET90</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>6</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET90</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>7</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET90</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>8</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET90</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>9</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET180</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>10</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET180</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>11</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET180</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>12</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET180</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>13</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET270</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>14</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET270</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>15</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET270</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>16</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET270</b></td>
<td>180</td>
<td>3</td>
</tr>
</table>
 



 


## -remarks
This function is declared inline in D3dkmdt.h as:

If the content being presented has to be rotated by the driver, the output of this function represents the total rotation (the <b>Rotate</b> member of the <a href="display.dxgk_presentflags">DXGK_PRESENTFLAGS</a> structure) that the driver needs to apply to the pixels provided in the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> operation. For more info, see <a href="https://msdn.microsoft.com/136CEDA5-2839-4E6E-A032-1A9222C769C6">Supporting Path-Independent Rotation</a>.

Here's an example of how this function can provide your driver with the info it needs to properly rotate content. When a portrait-first device is connected in clone mode to a landscape-first monitor and  the user changes the <b>Orientation</b> in the <b>Display</b> control panel to <b>Portrait</b>, this represents the default orientation of the portrait-first device. Therefore the driver should set a value of <a href="display.d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>.<b>D3DKMDT_VPPR_ROTATE90_OFFSET270</b> on the path. This function will then return a <i>Rotation</i> value of 1 (identity) to indicate that the content displayed on the clone path is not to be rotated.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

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
Version

</th>
<td width="70%">
DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>
</dt>
<dt>
<a href="display.d3dkmdt_vppr_get_content_rotation_part">D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART</a>
</dt>
<dt>
<a href="display.d3dkmdt_vppr_get_offset_rotation">D3DKMDT_VPPR_GET_OFFSET_ROTATION</a>
</dt>
<dt>
<a href="display.dxgk_presentflags">DXGK_PRESENTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VPPR_GET_CONTENT_ROTATION function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

