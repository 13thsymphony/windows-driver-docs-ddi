---
UID: NE:rilapitypes.RILIMSSIPREASON
title: RILIMSSIPREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipreason.htm
old-project: netvista
ms.assetid: bb3269d5-1e42-4e18-9d93-ad7f3f4de3f9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILIMSSIPREASON, RILIMSSIPREASON enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSIPREASON_MAX, RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE, netvista.rilimssipreason, ntddrilapitypes/RILIMSSIPREASON, ntddrilapitypes/RIL_IMSSIPREASON_MAX, ntddrilapitypes/RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILIMSSIPREASON
product: Windows
targetos: Windows
req.typenames: RILIMSSIPREASON
req.product: Windows 10 or later.
---

# RILIMSSIPREASON Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILIMSSIPREASON { 
  RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE,
  RIL_IMSSIPREASON_MAX
} RILIMSSIPREASON;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_IMSSIPREASON_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSIPREASON_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |