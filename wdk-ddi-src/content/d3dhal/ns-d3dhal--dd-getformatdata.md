---
UID: NS.d3dhal._DD_GETFORMATDATA
title: DD_GETFORMATDATA
author: windows-driver-content
description: DD_GETFORMATDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMAT.
old-location: display\dd_getformatdata.htm
old-project: display
ms.assetid: 881a52d1-8e37-4474-a943-086ef5ceca80
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_GETFORMATDATA, DD_GETFORMATDATA
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
req.alt-api: DD_GETFORMATDATA
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

# DD_GETFORMATDATA structure



## -description
<p><b>DirectX 8.0 and later versions only.</b></p>
<p>DD_GETFORMATDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMAT.</p>


## -syntax

````
typedef struct _DD_GETFORMATDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwFormatIndex;
  DDPIXELFORMAT         format;
} DD_GETFORMATDATA;
````


## -struct-fields
<dl>

### -field <b>gdi2</b>

<dd>
<p>Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.</p>
</dd>

### -field <b>dwFormatIndex</b>

<dd>
<p>Specifies the index of the pixel format to return.</p>
</dd>

### -field <b>format</b>

<dd>
<p>Receives the actual pixel format in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550274">DDPIXELFORMAT</a> structure.</p>
</dd>
</dl>

## -remarks
<p>The runtime identifies the format to be returned with an integer index whose value varies between zero and one less than the number of supported formats reported earlier by the driver. How these indices are mapped to actual formats is left to the driver. However, each index must map uniquely to one supported format. The order in which the formats are reported is not significant. </p>

<p>When processing this <b>GetDriverInfo2</b> request the driver should read the <b>dwFormatIndex</b> and map that to one of the supported formats (probably by using <b>dwFormatIndex</b> as an index into an array of DDPIXELFORMAT structures) and then copy that format into the format field of the DD_GETFORMATDATA field. The runtime guarantees that it only passes an index to the driver that is in the range zero to one less than the number of surface formats reported by the driver. The range of the index should be validated in the debug driver build.</p>

<p><b>DirectX 9.0 and later versions only.</b>On input, the version of the DirectX runtime that is being used by the application is specified in the <b>dwSize</b> member of the DDPIXELFORMAT structure in <b>format</b>. This <b>dwSize</b> member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550274">DDPIXELFORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETFORMATDATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
