---
UID: NS:iscsifnd._ISCSI_DiscoveredTarget
title: "_ISCSI_DiscoveredTarget"
author: windows-driver-content
description: The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget.htm
old-project: storage
ms.assetid: 0b4a7375-1ee2-4829-92bb-01ed610236de
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget structure [Storage Devices], PISCSI_DiscoveredTarget, PISCSI_DiscoveredTarget structure pointer [Storage Devices], _ISCSI_DiscoveredTarget, iscsifnd/ISCSI_DiscoveredTarget, iscsifnd/PISCSI_DiscoveredTarget, storage.iscsi_discoveredtarget, structs-iSCSI_d53d59a0-bd96-4eb8-b874-5846302ddda2.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
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
-	iscsifnd.h
api_name:
-	ISCSI_DiscoveredTarget
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget
---

# _ISCSI_DiscoveredTarget structure
The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.

## Syntax
```
typedef struct _ISCSI_DiscoveredTarget {
  ULONG                             TargetPortalGroupCount;
  WCHAR                             TargetName[223 + 1];
  WCHAR                             TargetAlias[255 + 1];
  ISCSI_DiscoveredTargetPortalGroup TargetDiscoveredPortalGroups[1];
} *PISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget;
```

## Members


`TargetPortalGroupCount`

The number of portal groups that are associated with the target.

`TargetName`

A name for the target that uniquely identifies the target anywhere in the world. For information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group.

`TargetAlias`

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, you should not use it in authentication decisions.

`TargetDiscoveredPortalGroups`

A variable-length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561515">ISCSI_DiscoveredTargetPortalGroup</a> structures that contains information about the portal groups that the initiator can use to connect to the target.

## Remarks
The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561527">ISCSI_DiscoveredTarget WMI Class</a> in <i>Discover.mof</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsifnd.h (include Iscsifnd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561527">ISCSI_DiscoveredTarget WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561503">ISCSI_DiscoveredTarget2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561515">ISCSI_DiscoveredTargetPortalGroup</a>