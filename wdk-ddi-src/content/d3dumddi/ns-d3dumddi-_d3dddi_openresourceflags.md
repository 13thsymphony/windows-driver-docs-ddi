---
UID: NS.D3DUMDDI._D3DDDI_OPENRESOURCEFLAGS
title: _D3DDDI_OPENRESOURCEFLAGS
author: windows-driver-content
description: The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.
old-location: display\d3dddi_openresourceflags.htm
old-project: display
ms.assetid: f65fda13-3d05-4e1b-b0c7-01e43a9bf09e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDI_OPENRESOURCEFLAGS, D3DDDI_OPENRESOURCEFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_OPENRESOURCEFLAGS
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

# _D3DDDI_OPENRESOURCEFLAGS structure



## -description
The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.



## -syntax

````
typedef struct _D3DDDI_OPENRESOURCEFLAGS {
  union {
    struct {
      UINT Fullscreen  :1;
      UINT AlphaOverride  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3DDDI_OPENRESOURCEFLAGS;
````


## -struct-fields

### -field Fullscreen

A UINT value that specifies whether the shared primary resource is used with a full-screen device.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field AlphaOverride

A UINT value that specifies whether to use the alpha channel in the shared primary resource. If <b>AlphaOverride</b> is set, the alpha channel should not be used.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_OPENRESOURCEFLAGS that can hold one 32-bit value that identifies the type of resource to open.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="display.d3dddiarg_openresource">D3DDDIARG_OPENRESOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OPENRESOURCEFLAGS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

