---
UID: NS.D3DUMDDI._D3DDDICB_FREEGPUVIRTUALADDRESS
title: _D3DDDICB_FREEGPUVIRTUALADDRESS
author: windows-driver-content
description: D3DDDICB_FREEGPUVIRTUALADDRESS is used with pfnFreeGpuVirtualAddressCb to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.
old-location: display\d3dddicb_freegpuvirtualaddress.htm
old-project: display
ms.assetid: 5E11C1BB-7E9E-4D9C-A15A-B9CCB29622C3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDICB_FREEGPUVIRTUALADDRESS, D3DDDICB_FREEGPUVIRTUALADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_FREEGPUVIRTUALADDRESS
req.alt-loc: d3dumddi.h
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

# _D3DDDICB_FREEGPUVIRTUALADDRESS structure



## -description
<b>D3DDDICB_FREEGPUVIRTUALADDRESS</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md">pfnFreeGpuVirtualAddressCb</a> to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.


## -syntax

````
typedef struct _D3DDDICB_FREEGPUVIRTUALADDRESS {
  D3DGPU_VIRTUAL_ADDRESS BaseAddress;
  D3DGPU_SIZE_T          Size;
} D3DDDICB_FREEGPUVIRTUALADDRESS;
````


## -struct-fields

### -field BaseAddress

Specifies the base virtual address, in bytes, of the range to free. Must be aligned to 4 KB.

### -field Size

Specifies the size, in bytes, of the range to free. Must be aligned to 4 KB.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md">pfnFreeGpuVirtualAddressCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_FREEGPUVIRTUALADDRESS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
