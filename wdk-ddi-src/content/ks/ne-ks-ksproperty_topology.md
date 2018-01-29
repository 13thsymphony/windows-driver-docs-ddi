---
UID : NE:ks.KSPROPERTY_TOPOLOGY
title : KSPROPERTY_TOPOLOGY
author : windows-driver-content
description : .
old-location : stream\ksproperty_topology.htm
old-project : stream
ms.assetid : 9C000B4B-DB21-41E1-9AF0-D3B92EAC070B
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksproperty_topology, ks/KSPROPERTY_TOPOLOGY_CATEGORIES, KSPROPERTY_TOPOLOGY enumeration [Streaming Media Devices], ks/KSPROPERTY_TOPOLOGY_NAME, KSPROPERTY_TOPOLOGY_CATEGORIES, KSPROPERTY_TOPOLOGY_CONNECTIONS, KSPROPERTY_TOPOLOGY, ks/KSPROPERTY_TOPOLOGY, KSPROPERTY_TOPOLOGY_NODES, ks/KSPROPERTY_TOPOLOGY_NODES, ks/KSPROPERTY_TOPOLOGY_CONNECTIONS, KSPROPERTY_TOPOLOGY_NAME
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ks.h
req.include-header : 
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
req.typenames : KSPROPERTY_TOPOLOGY
---

# KSPROPERTY_TOPOLOGY Enumeration


## Syntax
````
typedef enum  { 
  KSPROPERTY_TOPOLOGY_CATEGORIES,
  KSPROPERTY_TOPOLOGY_NODES,
  KSPROPERTY_TOPOLOGY_CONNECTIONS,
  KSPROPERTY_TOPOLOGY_NAME
} KSPROPERTY_TOPOLOGY;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_TOPOLOGY_CATEGORIES</td>
<td>Specify to query for the array of functional categories that a driver supports.</td>
</tr>

<tr>
<td>KSPROPERTY_TOPOLOGY_CONNECTIONS</td>
<td>Specify to query all connections between nodes of a KS filter.</td>
</tr>

<tr>
<td>KSPROPERTY_TOPOLOGY_NAME</td>
<td>Specify to provide the localized Unicode string name of the node.</td>
</tr>

<tr>
<td>KSPROPERTY_TOPOLOGY_NODES</td>
<td>Specify for a list of the topology nodes and node types GUIDs supported by the filter.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |