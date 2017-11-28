---
UID: NS.d3dhal._DD_DXVERSION
title: DD_DXVERSION
author: windows-driver-content
description: DirectX 8.0 and later versions only. DD_DXVERSION describes the current DirectX runtime version.
old-location: display\dd_dxversion.htm
old-project: display
ms.assetid: 72c22f76-c867-4924-b066-2ae4b25bfc43
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_DXVERSION, DD_DXVERSION
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
req.alt-api: DD_DXVERSION
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

# DD_DXVERSION structure



## -description
<p>
   DirectX 8.0 and later versions only.
   </p>
<p>DD_DXVERSION describes the current DirectX runtime version. </p>


## -syntax

````
typedef struct _DD_DXVERSION {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwDXVersion;
  DWORD                 dwReserved;
} DD_DXVERSION;
````


## -struct-fields
<dl>

### -field <b>gdi2</b>

<dd>
<p>Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.</p>
</dd>

### -field <b>dwDXVersion</b>

<dd>
<p>Specifies the version of DirectX. This member is set to DD_RUNTIME_VERSION, which is 0x00000700 for DirectX 7.0 and 0x00000800 for DirectX 8.0.</p>
</dd>

### -field <b>dwReserved</b>

<dd>
<p>Reserved. Driver should not read or write.</p>
</dd>
</dl>

## -remarks
<p>This information is provided to a new driver (one that exposes <b>GetDriverInfo2</b>) for DX7 and DX8 applications.</p>

<p>The runtime provides a pointer to a DD_DXVERSION structure in the <b>lpvData</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> data structure.</p>

<p>The <b>gdi2</b> member of DD_DXVERSION is used by the runtime with type D3DGDI2_TYPE_DXVERSION specified to notify the driver of the current DirectX runtime version being used by the application.</p>

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
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_DXVERSION structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
