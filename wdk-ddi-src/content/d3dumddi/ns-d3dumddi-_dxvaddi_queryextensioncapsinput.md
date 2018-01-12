---
UID: NS:d3dumddi._DXVADDI_QUERYEXTENSIONCAPSINPUT
title: _DXVADDI_QUERYEXTENSIONCAPSINPUT
author: windows-driver-content
description: The DXVADDI_QUERYEXTENSIONCAPSINPUT structure describes a capability of an extension GUID that information is requested for.
old-location: display\dxvaddi_queryextensioncapsinput.htm
old-project: display
ms.assetid: 6907eb45-8d29-4cdc-80eb-2d8cafbbd9bd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVADDI_QUERYEXTENSIONCAPSINPUT, DXVADDI_QUERYEXTENSIONCAPSINPUT
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
req.alt-api: DXVADDI_QUERYEXTENSIONCAPSINPUT
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
req.typenames: DXVADDI_QUERYEXTENSIONCAPSINPUT
---

# _DXVADDI_QUERYEXTENSIONCAPSINPUT structure



## -description
The DXVADDI_QUERYEXTENSIONCAPSINPUT structure describes a capability of an extension GUID that information is requested for.



## -syntax

````
typedef struct _DXVADDI_QUERYEXTENSIONCAPSINPUT {
  const GUID          *pGuid;
  UINT                CapType;
  DXVADDI_PRIVATEDATA *pPrivate;
} DXVADDI_QUERYEXTENSIONCAPSINPUT;
````


## -struct-fields

### -field pGuid

[in] A pointer to a GUID that represents the extension device type. 


### -field CapType

[in] A capability type that information is requested for. A capability type can apply to one of the following categories of video acceleration:

<ul>
<li>
DXVADDI_EXTENSION_CATEGORY_DECODER (0x0001)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_ENCODER (0x0002)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_PROCESSOR (0x0004)

</li>
<li>
DXVADDI_EXTENSION_CATEGORY_ALL (0x0007)

</li>
</ul>
Extension capability types can be defined from DXVADDI_EXTENSION_CAPTYPE_MIN (300) to DXVADDI_EXTENSION_CAPTYPE_MAX (400).


### -field pPrivate

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to retrieve information about the extension capability.


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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_QUERYEXTENSIONCAPSINPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

