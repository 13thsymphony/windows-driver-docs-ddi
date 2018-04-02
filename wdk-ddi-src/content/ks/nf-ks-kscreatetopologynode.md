---
UID: NF:ks.KsCreateTopologyNode
title: KsCreateTopologyNode function
author: windows-driver-content
description: The KsCreateTopologyNode function creates a handle to a topology node instance. The function can only be called at PASSIVE_LEVEL.
old-location: stream\kscreatetopologynode.htm
old-project: stream
ms.assetid: aeed8086-b413-428c-b275-d555523b5503
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreateTopologyNode, KsCreateTopologyNode function [Streaming Media Devices], ks/KsCreateTopologyNode, ksfunc_15092cdb-3f97-4f13-a10e-9dbc92d20776.xml, stream.kscreatetopologynode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsCreateTopologyNode
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsCreateTopologyNode function
The <b>KsCreateTopologyNode</b> function creates a handle to a topology node instance. The function can only be called at <b>PASSIVE_LEVEL</b>.

## Syntax

```
KSDDKAPI NTSTATUS KsCreateTopologyNode(
  HANDLE         ParentHandle,
  PKSNODE_CREATE NodeCreate,
  ACCESS_MASK    DesiredAccess,
  PHANDLE        NodeHandle
);
```

## Parameters

`ParentHandle`

Specifies the handle to the parent on which the node is created.

`NodeCreate`

Specifies topology node create parameters.

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.

`NodeHandle`

Location for the topology node handle.


## Return Value

Returns <b>STATUS_SUCCESS</b>, or an error if unable to create a node.

## Remarks

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff563471">KSNODE_CREATE</a> structure describes the set of information used to create the node handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563471">KSNODE_CREATE</a>