---
UID: NS.d3dkmdt._D3DKMDT_VIDPN_HW_CAPABILITY
title: D3DKMDT_VIDPN_HW_CAPABILITY
author: windows-driver-content
description: The D3DKMDT_VIDPN_HW_CAPABILITY structure describes the capabilities of the display miniport driver to perform display operations on a specified functional VidPN without dedicated GPU hardware support.
old-location: display\d3dkmdt_vidpn_hw_capability.htm
old-project: display
ms.assetid: 8d881133-3ea7-43c4-99cc-d843026573d6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMDT_VIDPN_HW_CAPABILITY,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_HW_CAPABILITY
req.alt-loc: d3dkmdt.h
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

# D3DKMDT_VIDPN_HW_CAPABILITY structure



## -description
<p>The D3DKMDT_VIDPN_HW_CAPABILITY structure describes the capabilities of the display miniport driver to perform display operations on a specified functional VidPN without dedicated GPU hardware support. For definitions of hardware terminology used in this topic, see the Remarks section.</p>


## -syntax

````
typedef struct _D3DKMDT_VIDPN_HW_CAPABILITY {
  UINT DriverRotation  :1;
  UINT DriverScaling  :1;
  UINT DriverCloning  :1;
  UINT DriverColorConvert  :1;
  UINT DriverLinkedAdapaterOutput  :1;
  UINT DriverRemoteDisplay  :1;
  UINT Reserved  :26;
} D3DKMDT_VIDPN_HW_CAPABILITY;
````


## -struct-fields
<dl>

### -field DriverRotation

<dd>
<p>A UINT value that describes the capability of the display miniport driver to display a rotated image.</p>
<p>If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the rotated image and then uses display pipeline hardware to display the rotated image.</p>
<p>If set to 0, the driver uses display pipeline hardware to directly generate the rotated image.</p>
</dd>

### -field DriverScaling

<dd>
<p>A UINT value that describes the capability of the display miniport driver to display a scaled image.</p>
<p>If set to a nonzero value, the driver uses software or the system-supplied graphics engine to scale the on-screen image and then uses display pipeline hardware to display the scaled image.</p>
<p>If set to 0, the driver uses display pipeline hardware to directly generate the scaled image.</p>
</dd>

### -field DriverCloning

<dd>
<p>A UINT value that describes the capability of the display miniport driver to display a cloned image.</p>
<p>If set to a nonzero value, the driver uses software or the system-supplied graphics engine to copy the on-screen image and then uses display pipeline hardware to display the copy.</p>
<p>If set to 0, the driver uses display pipeline hardware to directly generate the cloned image.</p>
</dd>

### -field DriverColorConvert

<dd>
<p>A UINT value that describes the capability of the display miniport driver to display a color-convert bit-block transfer (bitblt).</p>
<p>If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the color-convert bitblt and then uses display pipeline hardware to display the color-converted image. For example, if the display pipeline hardware cannot color-convert from an 8-bit palletized surface format (defined by the D3DDDIFMT_P8 value of the <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a> enumeration), the driver can use the graphics engine to perform a color-convert bitblt from the D3DDDIFMT_ P8 format to the D3DDDIFMT_R8G8B8 format and then render the new D3DDDIFMT_R8G8B8 image using the display pipeline hardware.</p>
<p>If set to 0, the driver uses display pipeline hardware to directly generate the color-converted image.</p>
</dd>

### -field DriverLinkedAdapaterOutput

<dd>
<p>A UINT value that describes the capability of the display miniport driver to perform a bit-block transfer (bitblt) of a primary surface from one linked display adapter to another linked display adapter.</p>
<p>If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the bitblt from the on-screen image on the first linked display adapter and then uses the second linked display adapter to display the bitblt image on the second display device.</p>
<p>If set to 0, the driver uses display pipeline hardware to directly generate the bitblt from the first linked display adapter and to display it with the second linked display adapter.</p>
</dd>

### -field DriverRemoteDisplay

<dd>
<p>A UINT value that describes whether the display pipeline hardware is located on the same device as the GPU graphics rendering pipeline.</p>
<p>If set to a nonzero value, the display pipeline hardware is not located on the same device as the GPU graphics rendering pipeline, and the primary surface might have to be transmitted over a bus that is not designed specifically for display image transfers. Examples of such remote display situations are a display monitor that is connected to the computer with a USB bus and a display that is connected remotely over a network.</p>
<p>If set to 0, the display pipeline hardware is located on the same device as the GPU graphics rendering pipeline.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use. The display miniport driver must set this value to 0.</p>
</dd>
</dl>

## -remarks
<p>The following definitions of terms are used in this topic.</p>

<p></p>

<p>Describes the components on the display device that generate the video signal from the image.</p>

<p>Describes the components on the display device that perform 3-D image rendering.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_HW_CAPABILITY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
