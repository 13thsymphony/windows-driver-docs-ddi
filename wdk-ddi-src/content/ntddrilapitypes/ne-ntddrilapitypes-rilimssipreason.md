---
UID: NE:ntddrilapitypes.RILIMSSIPREASON
title: RILIMSSIPREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipreason.htm
old-project: netvista
ms.assetid: bb3269d5-1e42-4e18-9d93-ad7f3f4de3f9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILIMSSIPREASON, netvista.rilimssipreason, RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE, ntddrilapitypes/RIL_IMSSIPREASON_MAX, ntddrilapitypes/RILIMSSIPREASON, ntddrilapitypes/RIL_IMSSIPREASON_NOT_AUTHORIZED_FOR_SERVICE, RIL_IMSSIPREASON_MAX, RILIMSSIPREASON enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILIMSSIPREASON
product: Windows
targetos: Windows
req.typenames: RILIMSSIPREASON
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
| **Header** | ntddrilapitypes.h |