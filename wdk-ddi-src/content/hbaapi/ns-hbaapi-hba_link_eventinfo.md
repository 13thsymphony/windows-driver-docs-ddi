---
UID: NS:hbaapi.HBA_Link_EventInfo
title: HBA_Link_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API.
old-location: storage\hba_link_eventinfo.htm
old-project: storage
ms.assetid: be682bc7-61cb-40bd-920d-bc2224d6e426
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBA_LINK_EVENTINFO, HBA_LINK_EVENTINFO, HBA_LINK_EVENTINFO structure [Storage Devices], HBA_Link_EventInfo, HBA_Link_EventInfo structure [Storage Devices], PHBA_LINK_EVENTINFO, PHBA_LINK_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_Link_EventInfo, hbaapi/PHBA_LINK_EVENTINFO, storage.hba_link_eventinfo, structs-Fibre_eb994375-ebac-41f5-af82-341f14400b1f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_LINK_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO
---

# HBA_Link_EventInfo structure
The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API.

## Syntax
````
typedef struct HBA_Link_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 Reserved[3];
} HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO;
````

## Members


`PortFcId`

Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.

`Reserved`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_rscn_eventinfo.md">HBA_RSCN_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_pty_eventinfo.md">HBA_Pty_EventInfo</a>