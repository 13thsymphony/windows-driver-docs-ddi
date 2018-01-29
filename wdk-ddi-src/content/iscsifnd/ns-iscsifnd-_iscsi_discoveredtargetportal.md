---
UID : NS:iscsifnd._ISCSI_DiscoveredTargetPortal
title : _ISCSI_DiscoveredTargetPortal
author : windows-driver-content
description : The ISCSI_DiscoveredTargetPortal structure provides information that is associated with a discovered target portal.
old-location : storage\iscsi_discoveredtargetportal.htm
old-project : storage
ms.assetid : af5d0ad6-a035-4291-9390-889fdc3429ee
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : iscsifnd/ISCSI_DiscoveredTargetPortal, PISCSI_DiscoveredTargetPortal, PISCSI_DiscoveredTargetPortal structure pointer [Storage Devices], ISCSI_DiscoveredTargetPortal, storage.iscsi_discoveredtargetportal, _ISCSI_DiscoveredTargetPortal, iscsifnd/PISCSI_DiscoveredTargetPortal, structs-iSCSI_956c4a5b-9f37-4b76-b2e8-d8feedaddcf0.xml, ISCSI_DiscoveredTargetPortal structure [Storage Devices], *PISCSI_DiscoveredTargetPortal
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsifnd.h
req.include-header : Iscsifnd.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PISCSI_DiscoveredTargetPortal, ISCSI_DiscoveredTargetPortal"
---

# _ISCSI_DiscoveredTargetPortal structure
The ISCSI_DiscoveredTargetPortal structure provides information that is associated with a discovered target portal.

## Syntax
````
typedef struct _ISCSI_DiscoveredTargetPortal {
  USHORT           Socket;
  ISCSI_IP_Address Address;
  WCHAR            SymbolicName[256 + 1];
} ISCSI_DiscoveredTargetPortal, *PISCSI_DiscoveredTargetPortal;
````

## Members


`Address`

The network address of the portal.

`Socket`

The socket number of the portal.

`SymbolicName`

A wide character string that indicates the portal's symbolic name.

## Remarks
The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortal structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a> in <i>Discover.mof</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iscsifnd.h (include Iscsifnd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a>

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportal2.md">ISCSI_DiscoveredTargetPortal2</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTargetPortal structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>