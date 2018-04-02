---
UID: NS:ks.KSE_NODE
title: KSE_NODE
author: windows-driver-content
description: The KSE_NODE structure specifies an event request on a specific node.
old-location: stream\kse_node.htm
old-project: stream
ms.assetid: 89446165-cdc3-414d-bcce-f2c978d94547
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSE_NODE, KSE_NODE, KSE_NODE structure [Streaming Media Devices], PKSE_NODE, PKSE_NODE structure pointer [Streaming Media Devices], ks-struct_701a51ab-90d7-47d6-8e40-bd30d0ddd7b9.xml, ks/KSE_NODE, ks/PKSE_NODE, stream.kse_node"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSE_NODE
product: Windows
targetos: Windows
req.typenames: KSE_NODE, *PKSE_NODE
---

# KSE_NODE structure
The KSE_NODE structure specifies an event request on a specific node.

## Syntax
```
typedef struct KSE_NODE {
  KSEVENT Event;
  ULONG   NodeId;
  ULONG   Reserved;
}  *PKSE_NODE;
```

## Members


`Event`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a> that identifies the requested event.

`NodeId`

Specifies the node ID.

`Reserved`

Reserved for system use. Should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a>