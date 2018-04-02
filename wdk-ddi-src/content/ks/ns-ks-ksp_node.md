---
UID: NS:ks.KSP_NODE
title: KSP_NODE
author: windows-driver-content
description: Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.
old-location: stream\ksp_node.htm
old-project: stream
ms.assetid: 2d5f1b31-d8fe-40a3-ac23-cc442f3adbe5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSP_NODE, KSP_NODE, KSP_NODE structure [Streaming Media Devices], PKSP_NODE, PKSP_NODE structure pointer [Streaming Media Devices], ks-struct_e93685c5-c84a-469a-ad2c-2407cb2e383b.xml, ks/KSP_NODE, ks/PKSP_NODE, stream.ksp_node"
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
-	KSP_NODE
product:
- Windows
targetos: Windows
req.typenames: KSP_NODE, *PKSP_NODE
---

# KSP_NODE structure
Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.

## Syntax
```
typedef struct KSP_NODE {
  KSPROPERTY Property;
  ULONG      NodeId;
  ULONG      Reserved;
}  *PKSP_NODE;
```

## Members


`Property`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure.

`NodeId`

Specifies the node ID.

`Reserved`

Reserved for system use. Should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537143">KSNODEPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>