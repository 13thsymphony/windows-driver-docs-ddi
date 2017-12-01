---
UID: NE.dxgiddi.DXGI_DDI_FLIP_INTERVAL_TYPE
title: DXGI_DDI_FLIP_INTERVAL_TYPE
author: windows-driver-content
description: The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\dxgi_ddi_flip_interval_type.htm
old-project: display
ms.assetid: e33da768-9d57-4b07-9c4e-c86d19828291
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DxApiGetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_FLIP_INTERVAL_TYPE
req.alt-loc: dxgiddi.h
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

# DXGI_DDI_FLIP_INTERVAL_TYPE enumeration



## -description
<p>The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.</p>


## -syntax

````
typedef enum DXGI_DDI_FLIP_INTERVAL_TYPE { 
  DXGI_DDI_FLIP_INTERVAL_IMMEDIATE  = 0,
  DXGI_DDI_FLIP_INTERVAL_ONE        = 1,
  DXGI_DDI_FLIP_INTERVAL_TWO        = 2,
  DXGI_DDI_FLIP_INTERVAL_THREE      = 3,
  DXGI_DDI_FLIP_INTERVAL_FOUR       = 4
} DXGI_DDI_FLIP_INTERVAL_TYPE;
````


## -enum-fields
<dl>

### -field <a id="DXGI_DDI_FLIP_INTERVAL_IMMEDIATE"></a><a id="dxgi_ddi_flip_interval_immediate"></a><b>DXGI_DDI_FLIP_INTERVAL_IMMEDIATE</b>

<dd>
<p>Indicates to perform the flip immediately without waiting for a vertical sync to occur. </p>
</dd>

### -field <a id="DXGI_DDI_FLIP_INTERVAL_ONE"></a><a id="dxgi_ddi_flip_interval_one"></a><b>DXGI_DDI_FLIP_INTERVAL_ONE</b>

<dd>
<p>Indicates to perform the flip on every vertical sync. </p>
</dd>

### -field <a id="DXGI_DDI_FLIP_INTERVAL_TWO"></a><a id="dxgi_ddi_flip_interval_two"></a><b>DXGI_DDI_FLIP_INTERVAL_TWO</b>

<dd>
<p>Indicates to perform the flip on every other vertical sync. </p>
</dd>

### -field <a id="DXGI_DDI_FLIP_INTERVAL_THREE"></a><a id="dxgi_ddi_flip_interval_three"></a><b>DXGI_DDI_FLIP_INTERVAL_THREE</b>

<dd>
<p>Indicates to perform the flip on every third vertical sync.</p>
</dd>

### -field <a id="DXGI_DDI_FLIP_INTERVAL_FOUR"></a><a id="dxgi_ddi_flip_interval_four"></a><b>DXGI_DDI_FLIP_INTERVAL_FOUR</b>

<dd>
<p>Indicates to perform the flip on every fourth vertical sync.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi-ddi-arg-present.md">DXGI_DDI_ARG_PRESENT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_FLIP_INTERVAL_TYPE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
