---
UID: NS:iscsidef._ISCSI_TargetPortalGroup
title: "_ISCSI_TargetPortalGroup"
author: windows-driver-content
description: The ISCSI_TargetPortalGroup structure provides a definition of a target portal group.
old-location: storage\iscsi_targetportalgroup.htm
old-project: storage
ms.assetid: 28f48224-90b8-45f5-b69d-6bb6a34f64e0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PISCSI_TargetPortalGroup, ISCSI_TargetPortalGroup, ISCSI_TargetPortalGroup structure [Storage Devices], PISCSI_TargetPortalGroup, PISCSI_TargetPortalGroup structure pointer [Storage Devices], _ISCSI_TargetPortalGroup, iscsidef/ISCSI_TargetPortalGroup, iscsidef/PISCSI_TargetPortalGroup, storage.iscsi_targetportalgroup, structs-iSCSI_27b8d554-5021-49d0-837c-302e7ac033ed.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
-	iscsidef.h
api_name:
-	ISCSI_TargetPortalGroup
product:
- Windows
targetos: Windows
req.typenames: ISCSI_TargetPortalGroup, *PISCSI_TargetPortalGroup
---

# _ISCSI_TargetPortalGroup structure
The ISCSI_TargetPortalGroup structure provides a definition of a target portal group.

## Syntax
```
typedef struct _ISCSI_TargetPortalGroup {
  ULONG              PortalCount;
  ISCSI_TargetPortal Portals[1];
} ISCSI_TargetPortalGroup, *PISCSI_TargetPortalGroup;
```

## Members


`PortalCount`

The number of portals in the portal group.

`Portals`

A variable-length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a> structures, which describe portals in the target portal group. The number of elements in the array is specified by the PortalCount field.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsidef.h (include Iscsidef.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561576">ISCSI_TargetPortalGroup WMI Class</a>