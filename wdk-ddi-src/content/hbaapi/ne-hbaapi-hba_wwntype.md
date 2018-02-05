---
UID : NE:hbaapi.HBA_wwntype
title : HBA_wwntype
author : windows-driver-content
description : The HBA_wwntype enumerator indicates whether a worldwide name specifies a port or a node (machine).
old-location : storage\hba_wwntype.htm
old-project : storage
ms.assetid : 30ce30db-e030-43c3-bf8d-2f6ef86087ab
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : HBA_wwntype enumeration [Storage Devices], PORT_WWN, hbaapi/HBA_wwntype, hbaapi/PORT_WWN, HBA_WWNTYPE enumeration [Storage Devices], hbaapi/NODE_WWN, NODE_WWN, HBA_WWNTYPE, structs-Fibre_d6003dc8-cbef-437b-bb14-353416b04417.xml, HBA_wwntype, storage.hba_wwntype
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HBA_WWNTYPE
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_wwntype enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>