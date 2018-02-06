---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortalGroup2
title: "_ISCSI_DiscoveredTargetPortalGroup2"
author: windows-driver-content
description: The ISCSI_DiscoveredTargetPortalGroup2 structure contains information about a discovered target portal group.
old-location: storage\iscsi_discoveredtargetportalgroup2.htm
old-project: storage
ms.assetid: d852f062-3090-4a7a-bdb8-9dde93257a90
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.iscsi_discoveredtargetportalgroup2, _ISCSI_DiscoveredTargetPortalGroup2, PISCSI_DiscoveredTargetPortalGroup2 structure pointer [Storage Devices], structs-iSCSI_2135fea1-a4b9-401e-a7b3-9a1b1896fe28.xml, ISCSI_DiscoveredTargetPortalGroup2, ISCSI_DiscoveredTargetPortalGroup2 structure [Storage Devices], iscsifnd/PISCSI_DiscoveredTargetPortalGroup2, iscsifnd/ISCSI_DiscoveredTargetPortalGroup2, *PISCSI_DiscoveredTargetPortalGroup2, PISCSI_DiscoveredTargetPortalGroup2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsifnd.h
apiname:
-	ISCSI_DiscoveredTargetPortalGroup2
product: Windows
targetos: Windows
req.typenames: "*PISCSI_DiscoveredTargetPortalGroup2, ISCSI_DiscoveredTargetPortalGroup2"
---

# _ISCSI_DiscoveredTargetPortalGroup2 structure
The ISCSI_DiscoveredTargetPortalGroup2 structure contains information about a discovered target portal group.

## Syntax
````
typedef struct _ISCSI_DiscoveredTargetPortalGroup2 {
  ULONG                         PortalCount;
  USHORT                        Tag;
  ISCSI_DiscoveredTargetPortal2 Portals[1];
} ISCSI_DiscoveredTargetPortalGroup2, *PISCSI_DiscoveredTargetPortalGroup2;
````

## Members


`PortalCount`

The number of portals in the group.

`Portals`

An array of <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a> structures, which describe target portals.

`Tag`

A tag number that identifies the portal group.

## Remarks
The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortalGroup2 structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561520">ISCSI_DiscoveredTargetPortalGroup2 WMI Class</a> in <i>Discover.mof</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsifnd.h (include Iscsifnd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561520">ISCSI_DiscoveredTargetPortalGroup2 WMI Class</a>

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a>

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup.md">ISCSI_DiscoveredTargetPortalGroup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561523">ISCSI_DiscoveredTargetPortalGroup WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTargetPortalGroup2 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>