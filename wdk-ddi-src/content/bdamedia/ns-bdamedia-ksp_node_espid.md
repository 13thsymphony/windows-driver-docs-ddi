---
UID : NS:bdamedia.KSP_NODE_ESPID
title : KSP_NODE_ESPID
author : windows-driver-content
description : The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.
old-location : stream\ksp_node_espid.htm
old-project : stream
ms.assetid : c5d0dbd8-bcce-436b-8fa7-bcb2b5c4ba59
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSP_NODE_ESPID, *PKSP_NODE_ESPID, PKSP_NODE_ESPID structure pointer [Streaming Media Devices], bdamedia/KSP_NODE_ESPID, bdamedia/PKSP_NODE_ESPID, KSP_NODE_ESPID structure [Streaming Media Devices], stream.ksp_node_espid, PKSP_NODE_ESPID, bdaref_aef92a8d-df0e-4283-b06a-4ece33b91809.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdamedia.h
req.include-header : Bdamedia.h
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
req.typenames : KSP_NODE_ESPID, *PKSP_NODE_ESPID
---

# KSP_NODE_ESPID structure
The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.

## Syntax
````
typedef struct {
  KSP_NODE Property;
  ULONG    EsPid;
} KSP_NODE_ESPID, *PKSP_NODE_ESPID;
````

## Members


`EsPid`

Packet identifier (PID) that identifies packets in the elementary stream.

`Property`

KSP_NODE structure that describes a property and node type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdamedia.h (include Bdamedia.h) |

## See Also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSP_NODE_ESPID structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>