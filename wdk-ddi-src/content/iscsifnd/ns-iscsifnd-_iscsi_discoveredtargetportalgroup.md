---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortalGroup
title: "_ISCSI_DiscoveredTargetPortalGroup"
author: windows-driver-content
description: The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.
old-location: storage\iscsi_discoveredtargetportalgroup.htm
old-project: storage
ms.assetid: 5c90dbc2-f42a-4c04-8c77-0ef3a712416c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_DiscoveredTargetPortalGroup, ISCSI_DiscoveredTargetPortalGroup, ISCSI_DiscoveredTargetPortalGroup structure [Storage Devices], PISCSI_DiscoveredTargetPortalGroup, PISCSI_DiscoveredTargetPortalGroup structure pointer [Storage Devices], _ISCSI_DiscoveredTargetPortalGroup, iscsifnd/ISCSI_DiscoveredTargetPortalGroup, iscsifnd/PISCSI_DiscoveredTargetPortalGroup, storage.iscsi_discoveredtargetportalgroup, structs-iSCSI_aa46b46a-73cf-4d06-a5ff-9abc5794f965.xml"
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
-	ISCSI_DiscoveredTargetPortalGroup
product: Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTargetPortalGroup, *PISCSI_DiscoveredTargetPortalGroup
---

# _ISCSI_DiscoveredTargetPortalGroup structure
The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.

## Syntax
````
typedef struct _ISCSI_DiscoveredTargetPortalGroup {
  ULONG                        PortalCount;
  ISCSI_DiscoveredTargetPortal Portals[1];
} ISCSI_DiscoveredTargetPortalGroup, *PISCSI_DiscoveredTargetPortalGroup;
````

## Members


`PortalCount`

The number of portals in the group.

`Portals`

An array of <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a> structures, which describe target portals.

## Remarks
The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortalGroup structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561523">ISCSI_DiscoveredTargetPortalGroup WMI Class</a> in <i>Discover.mof</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsifnd.h (include Iscsifnd.h) |

## See Also

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup2.md">ISCSI_DiscoveredTargetPortalGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561523">ISCSI_DiscoveredTargetPortalGroup WMI Class</a>



<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTargetPortalGroup structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>