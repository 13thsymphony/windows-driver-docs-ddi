---
UID: NS:pcivirt._SRIOV_PNP_EVENT_COMPLETE
title: "_SRIOV_PNP_EVENT_COMPLETE"
author: windows-driver-content
description: Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the IOCTL_SRIOV_EVENT_COMPLETE request.
old-location: pci\sriov_pnp_event_complete.htm
old-project: PCI
ms.assetid: 3b40d780-8084-4c19-bb8e-9d1ab3dadc95
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_PNP_EVENT_COMPLETE, PCI.sriov_pnp_event_complete, SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE structure [Buses], _SRIOV_PNP_EVENT_COMPLETE, pcivirt/SRIOV_PNP_EVENT_COMPLETE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	SRIOV_PNP_EVENT_COMPLETE
product: Windows
targetos: Windows
req.typenames: SRIOV_PNP_EVENT_COMPLETE, *PSRIOV_PNP_EVENT_COMPLETE
---

# _SRIOV_PNP_EVENT_COMPLETE structure
Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a> request.

## Syntax
````
typedef struct _SRIOV_PNP_EVENT_COMPLETE {
  NTSTATUS  QueryStatus;
} SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE;
````

## Members


`QueryStatus`

Indicates the status to be returned in the PnP query IRP that is currently pended in the PF driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pcivirt.h |

## See Also

<a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>