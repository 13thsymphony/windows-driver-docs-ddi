---
UID: NE:hbaapi.HBA_wwntype
title: HBA_wwntype
author: windows-driver-content
description: The HBA_wwntype enumerator indicates whether a worldwide name specifies a port or a node (machine).
old-location: storage\hba_wwntype.htm
old-project: storage
ms.assetid: 30ce30db-e030-43c3-bf8d-2f6ef86087ab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_WWNTYPE, HBA_WWNTYPE enumeration [Storage Devices], HBA_wwntype, HBA_wwntype enumeration [Storage Devices], NODE_WWN, PORT_WWN, hbaapi/HBA_wwntype, hbaapi/NODE_WWN, hbaapi/PORT_WWN, storage.hba_wwntype, structs-Fibre_d6003dc8-cbef-437b-bb14-353416b04417.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_WWNTYPE
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_wwntype Enumeration
The HBA_wwntype enumerator indicates whether a worldwide name specifies a port or a node (machine).

## Syntax
````
typedef enum HBA_wwntype { 
  NODE_WWN  = 0,
  PORT_WWN  = 1
} HBA_WWNTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NODE_WWN</td>
                    <td>Indicates that the world wide name specifies a node..</td>
                </tr>
            
                <tr>
                    <td>PORT_WWN</td>
                    <td>Indicates that the world wide name specifies a port.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\nf-hbaapi-hba_sendrnid.md">HBA_SendRNID</a>