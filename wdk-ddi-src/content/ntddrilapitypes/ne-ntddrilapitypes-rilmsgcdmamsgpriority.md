---
UID: NE:ntddrilapitypes.RILMSGCDMAMSGPRIORITY
title: RILMSGCDMAMSGPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgpriority.htm
old-project: netvista
ms.assetid: aec67cd5-9ac9-41da-b5e6-a4e416923afb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmsgcdmamsgpriority, RILMSGCDMAMSGPRIORITY enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILMSGCDMAMSGPRIORITY, ntddrilapitypes/RIL_MSGPRIORITY_HIGH, RIL_MSGPRIORITY_HIGH, ntddrilapitypes/RIL_MSGPRIORITY_EMERGENCY, RIL_MSGPRIORITY_MAX, RILMSGCDMAMSGPRIORITY, RIL_MSGPRIORITY_URGENT, RIL_MSGPRIORITY_EMERGENCY, ntddrilapitypes/RIL_MSGPRIORITY_MAX, ntddrilapitypes/RIL_MSGPRIORITY_URGENT
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
-	RILMSGCDMAMSGPRIORITY
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGPRIORITY
---

# RILMSGCDMAMSGPRIORITY Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGCDMAMSGPRIORITY { 
  RIL_MSGPRIORITY_HIGH,
  RIL_MSGPRIORITY_URGENT,
  RIL_MSGPRIORITY_EMERGENCY,
  RIL_MSGPRIORITY_MAX
} RILMSGCDMAMSGPRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGPRIORITY_EMERGENCY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIORITY_HIGH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIORITY_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIORITY_NORMAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPRIORITY_URGENT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |