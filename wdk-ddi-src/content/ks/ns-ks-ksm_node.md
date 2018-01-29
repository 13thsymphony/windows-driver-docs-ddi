---
UID : NS:ks.KSM_NODE
title : KSM_NODE
author : windows-driver-content
description : Just as KSP_NODE is used for properties on a node, the KSM_NODE structure is used for methods on a node.
old-location : stream\ksm_node.htm
old-project : stream
ms.assetid : 0e3f5abb-bf66-40e9-b318-9f6215f3d56c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/PKSM_NODE, stream.ksm_node, KSM_NODE, ks/KSM_NODE, KSM_NODE structure [Streaming Media Devices], PKSM_NODE, PKSM_NODE structure pointer [Streaming Media Devices], ks-struct_14efff2f-6d11-4055-a4f8-35d9389589b8.xml, *PKSM_NODE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PKSM_NODE, KSM_NODE"
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

A structure of type <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> that specifies the requested method.

`NodeId`

Specifies the node ID.

`Reserved`

Reserved for system use. Should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSM_NODE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>