---
UID: NS.d3dhal._DD_MULTISAMPLEQUALITYLEVELSDATA
title: DD_MULTISAMPLEQUALITYLEVELSDATA
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_MULTISAMPLEQUALITYLEVELSDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS.
old-location: display\dd_multisamplequalitylevelsdata.htm
ms.assetid: ff8bc5d8-5d65-4752-9318-f775394ae2b9
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DD_MULTISAMPLEQUALITYLEVELSDATA
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
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
req.iface: 
---

# DD_MULTISAMPLEQUALITYLEVELSDATA structure



## -description
<p>
   DirectX 9.0 and later versions only.
   </p>
<p>DD_MULTISAMPLEQUALITYLEVELSDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS.</p>


## -syntax

````
typedef struct _DD_MULTISAMPLEQUALITYLEVELSDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  D3DFORMAT             Format;
  BOOL                  bFlip  :1;
  D3DMULTISAMPLE_TYPE   MSType  :31;
  DWORD                 QualityLevels;
} DD_MULTISAMPLEQUALITYLEVELSDATA;
````


## -struct-fields
<dl>

### -field <b>gdi2</b>

<dd>
<p>Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.</p>
</dd>

### -field <b>Format</b>

<dd>
<p>Uses a value from the D3DFORMAT enumeration to specify the surface format of the multiple-sampled render target.</p>
</dd>

### -field <b>bFlip</b>

<dd>
<p>Indicates the type of resolution. Set to <b>TRUE</b> (1) for flip-style resolution and to <b>FALSE</b> (0) for blt-style resolution.</p>
</dd>

### -field <b>MSType</b>

<dd>
<p>Uses a value from the D3DMULTISAMPLE_TYPE enumeration to specify the level of full-scene multisampling. If the display device supports maskable multisampling (more than one sample for a multiple-sample render-target format plus antialias support), the driver for the device must provide the number of quality levels for the D3DMULTISAMPLE_NONMASKABLE (1) enumerated value. </p>
</dd>

### -field <b>QualityLevels</b>

<dd>
<p>Receives the number of multiple-sample quality levels that the driver supports for the given render-target format.</p>
</dd>
</dl>

## -remarks
<p>The driver assigns an integer from 1 to 8 to the <b>QualityLevels</b> member. If the driver fails, ignores this D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS query, or returns a value that is out of range, but otherwise reports that it supports multisampling, then the runtime determines that the number of quality levels is 1. </p>

<p>When the runtime calls a driver's <a href="https://msdn.microsoft.com/015b94d7-427f-401d-b348-d4e9ec5cfe5d">DdCanCreateSurface</a>, <a href="https://msdn.microsoft.com/45c793ed-34e8-4a15-91f4-9a258c1842fd">DdCreateSurface</a>, or <a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a> functions to create a surface, the runtime encodes the number of multiple-sample quality levels into three bits (the DDSCAPS3_MULTISAMPLE_QUALITY_MASK mask) of the <b>dwCaps3</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550292">DDSCAPS2</a> structure.</p>

<p>For more information about D3DFORMAT and D3DMULTISAMPLE_TYPE, see the DirectX SDK documentation.</p>

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
<a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/015b94d7-427f-401d-b348-d4e9ec5cfe5d">DdCanCreateSurface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/45c793ed-34e8-4a15-91f4-9a258c1842fd">DdCreateSurface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550292">DDSCAPS2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_MULTISAMPLEQUALITYLEVELSDATA structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
