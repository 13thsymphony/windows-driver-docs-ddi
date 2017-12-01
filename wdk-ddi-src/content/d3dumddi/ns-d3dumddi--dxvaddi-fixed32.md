---
UID: NS.d3dumddi._DXVADDI_FIXED32
title: DXVADDI_FIXED32
author: windows-driver-content
description: The DXVADDI_FIXED32 structure describes a floating-point number from a 16.16 fixed-point number.
old-location: display\dxvaddi_fixed32.htm
old-project: display
ms.assetid: 4188c488-fda4-4596-96f5-f740a5cc9ffc
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVADDI_FIXED32, DXVADDI_FIXED32
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
req.alt-api: DXVADDI_FIXED32
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
req.iface: 
---

# DXVADDI_FIXED32 structure



## -description
<p>The DXVADDI_FIXED32 structure describes a floating-point number from a 16.16 fixed-point number. </p>


## -syntax

````
typedef struct _DXVADDI_FIXED32 {
  union {
    struct {
      USHORT Fraction;
      SHORT  Value;
    };
    LONG   ll;
  };
} DXVADDI_FIXED32;
````


## -struct-fields
<dl>

### -field <b>Fraction</b>

<dd>
<p>[in] A USHORT value that specifies the 16 bits after the decimal point.</p>
</dd>

### -field <b>Value</b>

<dd>
<p>[in] A SHORT value that specifies the 16 bits before the decimal point. </p>
</dd>

### -field <b>ll</b>

<dd>
<p>A 32-bit value that describes the 16.16 fixed-point number.</p>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvaddi-procampvalues.md">DXVADDI_PROCAMPVALUES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_FIXED32 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
