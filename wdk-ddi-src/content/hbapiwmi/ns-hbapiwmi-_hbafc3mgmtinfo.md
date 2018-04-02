---
UID: NS:hbapiwmi._HBAFC3MgmtInfo
title: "_HBAFC3MgmtInfo"
author: windows-driver-content
description: The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter.
old-location: storage\hbafc3mgmtinfo.htm
old-project: storage
ms.assetid: 96236605-36b0-48f5-85d6-512160692b5f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBAFC3MgmtInfo, HBAFC3MgmtInfo, HBAFC3MgmtInfo structure [Storage Devices], PHBAFC3MgmtInfo, PHBAFC3MgmtInfo structure pointer [Storage Devices], _HBAFC3MgmtInfo, hbapiwmi/HBAFC3MgmtInfo, hbapiwmi/PHBAFC3MgmtInfo, storage.hbafc3mgmtinfo, structs-Fibre_b128f553-eb08-4077-9dcb-7a7238ec220f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
api_name:
-	HBAFC3MgmtInfo
product: Windows
targetos: Windows
req.typenames: HBAFC3MgmtInfo, *PHBAFC3MgmtInfo
---

# _HBAFC3MgmtInfo structure
The HBAFC3MgmtInfo structure is used to report FC3 management information associated with a fibre channel adapter.

## Syntax
```
typedef struct _HBAFC3MgmtInfo {
  ULONGLONG UniqueAdapterId;
  UCHAR     wwn[8];
  ULONG     unittype;
  ULONG     PortId;
  ULONG     NumberOfAttachedNodes;
  USHORT    IPVersion;
  USHORT    UDPPort;
  UCHAR     IPAddress[16];
  USHORT    reserved;
  USHORT    TopologyDiscoveryFlags;
  ULONG     reserved1;
} *PHBAFC3MgmtInfo, HBAFC3MgmtInfo;
```

## Members


`UniqueAdapterId`

Contains a unique identifier for the adapter.

`wwn`

Contains a worldwide name for the adapter, as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`unittype`

Describes the type of HBA, as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`PortId`

Contains a value corresponding to the physical port number field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`NumberOfAttachedNodes`

Contains the number of nodes attached to the topology as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`IPVersion`

Contains the concatenated node management and IP version fields of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`UDPPort`

Indicates the value of the UDP/TCP port number field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`IPAddress`

Indicates the value of the IP address field of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`reserved`

Reserved.

`TopologyDiscoveryFlags`

Indicates the value of the vendor specific field in word 12 of the specific identification data as described in the T11 committee's <i>Fibre Channel HBA API </i>specification.

`reserved1`

Reserved.

## Remarks
FC-3 refers to the common services layer of the fibre channel protocol. It defines a set of services which are common across multiple ports of a node. For an explanation of the common services layer, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

The WMI tool suite generates a declaration of this structure automatically when it compiles the <b>HBAFC3MgmtInfo</b> WMI Class in <i>hbaapi.mof</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553939">GetFC3MgmtInfo</a>