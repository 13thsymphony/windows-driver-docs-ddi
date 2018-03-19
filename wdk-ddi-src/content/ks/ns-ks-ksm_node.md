---
UID: NS:ks.KSM_NODE
title: KSM_NODE
author: windows-driver-content
description: Just as KSP_NODE is used for properties on a node, the KSM_NODE structure is used for methods on a node.
old-location: stream\ksm_node.htm
old-project: stream
ms.assetid: 0e3f5abb-bf66-40e9-b318-9f6215f3d56c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSM_NODE, KSM_NODE, KSM_NODE structure [Streaming Media Devices], PKSM_NODE, PKSM_NODE structure pointer [Streaming Media Devices], ks-struct_14efff2f-6d11-4055-a4f8-35d9389589b8.xml, ks/KSM_NODE, ks/PKSM_NODE, stream.ksm_node"
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
-	KSM_NODE
product: Windows
targetos: Windows
req.typenames: KSM_NODE, *PKSM_NODE
---

# KSM_NODE structure
Just as <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> is used for properties on a node, the KSM_NODE structure is used for methods on a node.

## Syntax
````
typedef struct {
  KSMETHOD Method;
  ULONG    NodeId;
  ULONG    Reserved;
} KSM_NODE, *PKSM_NODE;
````

## Members


`Method`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> that specifies the requested method.

`NodeId`

Specifies the node ID.

`Reserved`

Reserved for system use. Should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>