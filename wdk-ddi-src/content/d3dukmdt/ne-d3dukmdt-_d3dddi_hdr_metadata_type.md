---
UID: NE:d3dukmdt._D3DDDI_HDR_METADATA_TYPE
title: "_D3DDDI_HDR_METADATA_TYPE"
author: windows-driver-content
description: Defines the format of HDR metadata.
old-location: display\d3dddi_hdr_metadata_type.htm
old-project: display
ms.assetid: C30C34BF-F67D-4838-B337-9EF0D85B27DA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddi_hdr_metadata_type, D3DDDI_HDR_METADATA_TYPE_HDR10, d3dukmdt/D3DDDI_HDR_METADATA_TYPE, D3DDDI_HDR_METADATA_TYPE_NONE, d3dukmdt/D3DDDI_HDR_METADATA_TYPE_HDR10, d3dukmdt/D3DDDI_HDR_METADATA_TYPE_NONE, D3DDDI_HDR_METADATA_TYPE, _D3DDDI_HDR_METADATA_TYPE, D3DDDI_HDR_METADATA_TYPE enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_HDR_METADATA_TYPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_HDR_METADATA_TYPE
---

# _D3DDDI_HDR_METADATA_TYPE Enumeration
Defines the format of HDR metadata.

## Syntax
````
typedef enum _D3DDDI_HDR_METADATA_TYPE { 
  D3DDDI_HDR_METADATA_TYPE_NONE                 = 0,
  D3DDDI_HDR_METADATA_TYPE_HDR10                = 1
} D3DDDI_HDR_METADATA_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_HDR_METADATA_TYPE_HDR10</td>
                    <td>The HDR metadata is defined using the D3DDDI_HDR_METADATA_HDR10 structure.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_HDR_METADATA_TYPE_NONE</td>
                    <td>No HDR metadata is present.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dukmdt.h |