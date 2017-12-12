---
UID: NS.NTDDSTOR._STORAGE_PHYSICAL_NODE_DATA
title: _STORAGE_PHYSICAL_NODE_DATA
author: windows-driver-content
description: Specifies the physical device data of a storage node.
old-location: storage\storage_physical_node_data.htm
old-project: storage
ms.assetid: F6C1EE86-FB1C-467D-9E03-B238CB132D1A
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_PHYSICAL_NODE_DATA, *PSTORAGE_PHYSICAL_NODE_DATA, STORAGE_PHYSICAL_NODE_DATA
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
req.alt-api: STORAGE_PHYSICAL_NODE_DATA
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

# _STORAGE_PHYSICAL_NODE_DATA structure



## -description
Specifies the physical device data of a storage node.



## -syntax

````
typedef struct _STORAGE_PHYSICAL_NODE_DATA {
  ULONG NodeId;
  ULONG AdapterCount;
  ULONG AdapterDataLength;
  ULONG AdapterDataOffset;
  ULONG DeviceCount;
  ULONG DeviceDataLength;
  ULONG DeviceDataOffset;
  ULONG Reserved[3];
} STORAGE_PHYSICAL_NODE_DATA, *PSTORAGE_PHYSICAL_NODE_DATA;
````


## -struct-fields

### -field NodeId

The hardware ID of the storage node.


### -field AdapterCount

A value of 0 or 1 that indicates the adapter count in the storage node.


### -field AdapterDataLength

The data length of the storage adapter in the storage node,  in units of kilobytes (1024 bytes).


### -field AdapterDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of <a href="storage.storage_physical_adapter_data">STORAGE_PHYSICAL_ADAPTER_DATA</a>.


### -field DeviceCount

A value less than or equal to 1.


### -field DeviceDataLength

The data length of the storage device in the storage node,  in units of kilobytes (1024 bytes).


### -field DeviceDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of <a href="storage.storage_physical_device_data">STORAGE_PHYSICAL_DEVICE_DATA</a>.


### -field Reserved[3]

Specifies if the storage adapter is reserved.


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