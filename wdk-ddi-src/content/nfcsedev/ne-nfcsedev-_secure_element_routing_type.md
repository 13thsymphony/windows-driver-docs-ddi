---
UID: NE:nfcsedev._SECURE_ELEMENT_ROUTING_TYPE
title: "_SECURE_ELEMENT_ROUTING_TYPE"
author: windows-driver-content
description: SECURE_ELEMENT_ROUTING_TYPE is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_routing_type.htm
old-project: nfpdrivers
ms.assetid: 1420D957-546E-4795-A545-B098C411CCA5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSECURE_ELEMENT_ROUTING_TYPE, RoutingTypeAid, RoutingTypeProtocol, RoutingTypeTech, SECURE_ELEMENT_ROUTING_TYPE, _SECURE_ELEMENT_ROUTING_TYPE, _SECURE_ELEMENT_ROUTING_TYPE enumeration [Near-Field Proximity Drivers], nfcsedev/RoutingTypeAid, nfcsedev/RoutingTypeProtocol, nfcsedev/RoutingTypeTech, nfcsedev/_SECURE_ELEMENT_ROUTING_TYPE, nfpdrivers._secure_element_routing_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfcsedev.h
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
-	nfcsedev.h
api_name:
-	SECURE_ELEMENT_ROUTING_TYPE
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ROUTING_TYPE, *PSECURE_ELEMENT_ROUTING_TYPE
---

# _SECURE_ELEMENT_ROUTING_TYPE Enumeration
SECURE_ELEMENT_ROUTING_TYPE
is a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table_entry.md">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.

## Syntax
````
typedef enum _SECURE_ELEMENT_ROUTING_TYPE { 
  RoutingTypeTech      = 0,
  RoutingTypeProtocol  = 1,
  RoutingTypeAid       = 2
} SECURE_ELEMENT_ROUTING_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RoutingTypeAid</td>
                    <td>NFC Forum AID-based routing type.</td>
                </tr>
            
                <tr>
                    <td>RoutingTypeProtocol</td>
                    <td>NFC Forum protocol-based routing type.</td>
                </tr>
            
                <tr>
                    <td>RoutingTypeTech</td>
                    <td>NFC Forum technology-based routing type.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |