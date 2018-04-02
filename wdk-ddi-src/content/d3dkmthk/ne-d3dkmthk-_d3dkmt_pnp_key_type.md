---
UID: NE:d3dkmthk._D3DKMT_PNP_KEY_TYPE
title: "_D3DKMT_PNP_KEY_TYPE"
author: windows-driver-content
description: An enum that indicates the type of PNP key.
old-location: display\d3dkmt_pnp_key_type.htm
old-project: display
ms.assetid: 48B173D5-56C3-4611-BC55-CB7A25D05352
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_PNP_KEY_HARDWARE, D3DKMT_PNP_KEY_SOFTWARE, D3DKMT_PNP_KEY_TYPE, D3DKMT_PNP_KEY_TYPE enumeration [Display Devices], _D3DKMT_PNP_KEY_TYPE, d3dkmthk/D3DKMT_PNP_KEY_HARDWARE, d3dkmthk/D3DKMT_PNP_KEY_SOFTWARE, d3dkmthk/D3DKMT_PNP_KEY_TYPE, display.d3dkmt_pnp_key_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_PNP_KEY_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_PNP_KEY_TYPE
---

# _D3DKMT_PNP_KEY_TYPE Enumeration
An enum that indicates the type of PNP key.

## Syntax
```
typedef enum _D3DKMT_PNP_KEY_TYPE {
  D3DKMT_PNP_KEY_HARDWARE  ,
  D3DKMT_PNP_KEY_SOFTWARE
} D3DKMT_PNP_KEY_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>D3DKMT_PNP_KEY_HARDWARE</td>
                    <td>Indicates that the key is a hardware key..</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_PNP_KEY_SOFTWARE</td>
                    <td>Indicates that the key is a software key.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |