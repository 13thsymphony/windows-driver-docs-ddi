---
UID: NE.xpsrassvc.__MIDL___MIDL_itf_xpsrassvc_0000_0004_0001
title: __MIDL___MIDL_itf_xpsrassvc_0000_0004_0001
author: windows-driver-content
description: XPSRAS_BACKGROUND_COLOR specifies the background clear color to be used by an XPS rasterizer:
old-location: print\xpsras_background_color.htm
old-project: print
ms.assetid: 0B4C1BAC-173E-42E9-8805-028FE165D49D
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: __MIDL___MIDL_itf_xpsrassvc_0000_0004_0001, XPSRAS_BACKGROUND_COLOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: XPSRAS_BACKGROUND_COLOR
req.alt-loc: xpsrassvc.h
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
req.product: Windows 10 or later.
---

# __MIDL___MIDL_itf_xpsrassvc_0000_0004_0001 enumeration



## -description
<b>XPSRAS_BACKGROUND_COLOR</b> specifies the background clear color to be used by an XPS rasterizer:


## -syntax

````
typedef enum _XPSRAS_BACKGROUND_COLOR { 
  XPSRAS_BACKGROUND_COLOR_TRANSPARENT  = 0,
  XPSRAS_BACKGROUND_COLOR_OPAQUE       = 1
} XPSRAS_BACKGROUND_COLOR;
````


## -enum-fields

### -field XPSRAS_BACKGROUND_COLOR_TRANSPARENT

Use transparent white as clear color.

### -field XPSRAS_BACKGROUND_COLOR_OPAQUE

Use opaque white as clear color.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Xpsrassvc.h (include Xpsrassvc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.ixpsrasterizationfactory2_createrasterizer">IXpsRasterizationFactory2::CreateRasterizer</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20XPSRAS_BACKGROUND_COLOR enumeration%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
