---
UID: NS.NTDDSTOR._STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
title: _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
author: windows-driver-content
description: Describes the physical topology of storage in a system.
old-location: storage\storage_physical_topology_descriptor.htm
old-project: storage
ms.assetid: FD5714DF-9D34-4396-86BC-40054C199A0E
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, *PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
req.alt-loc: Ntddstor.h
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
---

# _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure



## -description
Describes the physical topology of storage in a system.



## -syntax

````
typedef struct _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR {
  ULONG                      Version;
  ULONG                      Size;
  ULONG                      NodeCount;
  ULONG                      Reserved;
  STORAGE_PHYSICAL_NODE_DATA Node[ANYSIZE_ARRAY];
} STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, *PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR;
````


## -struct-fields

### -field Version

The version of the physical topology.


### -field Size

The total size of data in the system.


### -field NodeCount

The total number of storage nodes in the system.


### -field Reserved

Indicates if storage in the system is reserved.


### -field Node[ANYSIZE_ARRAY]

Describes the storage nodes in the system.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>