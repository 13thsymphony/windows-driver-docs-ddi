---
UID: NS.DXGIDDI.DXGI_DDI_ARG_BLT_FLAGS
title: DXGI_DDI_ARG_BLT_FLAGS
author: windows-driver-content
description: The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.
old-location: display\dxgi_ddi_arg_blt_flags.htm
old-project: display
ms.assetid: 812679d2-b05c-4533-b4b2-01b973b0d80f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_ARG_BLT_FLAGS, DXGI_DDI_ARG_BLT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_ARG_BLT_FLAGS
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
---

# DXGI_DDI_ARG_BLT_FLAGS structure



## -description
The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.


## -syntax

````
typedef struct DXGI_DDI_ARG_BLT_FLAGS {
  union {
    struct {
      UINT Resolve  :1;
      UINT Convert  :1;
      UINT Stretch  :1;
      UINT Present  :1;
      UINT Reserved  :28;
    };
    UINT   Value;
  };
} DXGI_DDI_ARG_BLT_FLAGS;
````


## -struct-fields

### -field Resolve

A UINT value that specifies that the bitblt resolves multiple samples to one pixel. 
Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Convert

A UINT value that specifies that the bitblt also performs a format conversion.
Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field Stretch

A UINT value that specifies that a stretching bitblt is performed.
Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

### -field Present

A UINT value that specifies that a presenting bitblt is performed.
Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that DXGI_DDI_ARG_BLT_FLAGS contains that can hold a 32-bit value that identifies the bitblt type. 

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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt.md">DXGI_DDI_ARG_BLT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_BLT_FLAGS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
