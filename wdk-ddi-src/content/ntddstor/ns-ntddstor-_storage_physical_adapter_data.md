---
UID: NS.NTDDSTOR._STORAGE_PHYSICAL_ADAPTER_DATA
title: _STORAGE_PHYSICAL_ADAPTER_DATA
author: windows-driver-content
description: Specifies the physical device data of a storage adapter.
old-location: storage\storage_physical_adapter_data.htm
old-project: storage
ms.assetid: 404A7AFC-291E-4056-9076-F9E62A07C9FB
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_PHYSICAL_ADAPTER_DATA, STORAGE_PHYSICAL_ADAPTER_DATA, PSTORAGE_PHYSICAL_ADAPTER_DATA, *PSTORAGE_PHYSICAL_ADAPTER_DATA
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
req.alt-api: STORAGE_PHYSICAL_ADAPTER_DATA
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

# _STORAGE_PHYSICAL_ADAPTER_DATA structure



## -description
Specifies the physical device data of a storage adapter.



## -syntax

````
typedef struct _STORAGE_PHYSICAL_ADAPTER_DATA {
  ULONG                           AdapterId;
  STORAGE_COMPONENT_HEALTH_STATUS HealthStatus;
  STORAGE_PROTOCOL_TYPE           CommandProtocol;
  STORAGE_SPEC_VERSION            SpecVersion;
  UCHAR                           Vendor[8];
  UCHAR                           Model[40];
  UCHAR                           FirmwareRevision[16];
  UCHAR                           PhysicalLocation[32];
  BOOLEAN                         ExpandedConnector;
  UCHAR                           Reserved0[3];
  ULONG                           Reserved1[3];
} STORAGE_PHYSICAL_ADAPTER_DATA, *PSTORAGE_PHYSICAL_ADAPTER_DATA;
````


## -struct-fields

### -field AdapterId

The hardware ID of the storage adapter.


### -field HealthStatus

Indicates the health status of a storage adapter, of type <a href="storage.storage_component_health_status">STORAGE_COMPONENT_HEALTH_STATUS</a>.


### -field CommandProtocol

Specifies the storage command protocols that are used between software and hardware, of type <a href="storage.storage_protocol_type">STORAGE_PROTOCOL_TYPE</a>.


### -field SpecVersion

Indicates the specification of the storage adapter, of type <a href="storage.storage_spec_version">STORAGE_SPEC_VERSION</a>.


### -field Vendor[8]

The vendor name of the storage adapter.


### -field Model[40]

The model name of the storage adapter.


### -field FirmwareRevision[16]

The revision number of the storage adapter.


### -field PhysicalLocation[32]

This member is reserved for future use.


### -field ExpandedConnector

Specifies if the storage adapter includes an expanded connector.


### -field Reserved0[3]

Specifies if the storage adapter is reserved.


### -field Reserved1[3]

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