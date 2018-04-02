---
UID: NS:hbaapi.HBA_RSCN_EventInfo
title: HBA_RSCN_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API.
old-location: storage\hba_rscn_eventinfo.htm
old-project: storage
ms.assetid: d726d974-a877-464d-9721-6caf8a8402bf
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_RSCN_EVENTINFO, HBA_RSCN_EVENTINFO, HBA_RSCN_EVENTINFO structure [Storage Devices], HBA_RSCN_EventInfo, HBA_RSCN_EventInfo structure [Storage Devices], PHBA_RSCN_EVENTINFO, PHBA_RSCN_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_RSCN_EventInfo, hbaapi/PHBA_RSCN_EVENTINFO, storage.hba_rscn_eventinfo, structs-Fibre_c0cb4c14-5ff5-44cb-abb4-08673227f193.xml"
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
-	HBA_RSCN_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO
---

# HBA_RSCN_EventInfo structure
The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API.

## Syntax
```
typedef struct HBA_RSCN_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 NPortPage;
  HBA_UINT32 Reserved[2];
} *PHBA_RSCN_EVENTINFO, HBA_RSCN_EVENTINFO;
```

## Members


`PortFcId`

Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.

`NPortPage`

Contains port page information. For information about what values this member can have, see section entitled "Affected N-Port Pages" in the <i>FC-FS </i>specification for RSCN ELS.

`Reserved`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556048">HBA_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556124">HBA_Link_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557125">HBA_Pty_EventInfo</a>