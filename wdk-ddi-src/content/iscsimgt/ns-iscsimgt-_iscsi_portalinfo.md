---
UID: NS:iscsimgt._ISCSI_PortalInfo
title: "_ISCSI_PortalInfo"
author: windows-driver-content
description: The ISCSI_PortalInfo structure contains information about an iSCSI portal.
old-location: storage\iscsi_portalinfo.htm
old-project: storage
ms.assetid: 0ecfed3e-477a-4014-8491-1a8997ac5b90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_PortalInfo, ISCSI_PortalInfo, ISCSI_PortalInfo structure [Storage Devices], PISCSI_PortalInfo, PISCSI_PortalInfo structure pointer [Storage Devices], _ISCSI_PortalInfo, iscsimgt/ISCSI_PortalInfo, iscsimgt/PISCSI_PortalInfo, storage.iscsi_portalinfo, structs-iSCSI_40fc24e8-364d-4698-911c-4128f471cdcd.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
api_name:
-	ISCSI_PortalInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_PortalInfo, *PISCSI_PortalInfo
---

# _ISCSI_PortalInfo structure
The ISCSI_PortalInfo structure contains information about an iSCSI portal.

## Syntax
````
typedef struct _ISCSI_PortalInfo {
  ULONG            Index;
  UCHAR            PortalType;
  UCHAR            Protocol;
  UCHAR            Reserved1;
  UCHAR            Reserved2;
  ISCSI_IP_Address IPAddr;
  ULONG            Port;
  USHORT           PortalTag;
} ISCSI_PortalInfo, *PISCSI_PortalInfo;
````

## Members


`Index`

The unique port number associated with this portal.

`PortalType`

The type of portal. This member can have the following symbolic constant values, which are defined in <i>Iscsimgt.h</i>.

<table>
<tr>
<th>Portal Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
InitiatorPortals

</td>
<td>
The portal that the initiator uses to access the network. In an initiator, a portal is identified by its IP address. 

</td>
</tr>
<tr>
<td>
TargetPortals

</td>
<td>
The portal that the target uses to access the network. In a target, a portal is identified by its IP address and its listening TCP port.

</td>
</tr>
</table>

`Protocol`

The portal's transport protocol. Currently, this member must hold the value that is associated with the symbolic constant, TCP. TCP is defined in <i>Iscsimgt.h</i>.

`Reserved1`

Reserved for Microsoft use only.

`Reserved2`

Reserved for Microsoft use only.

`IPAddr`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that indicates the portal's network IP address.

`Port`

The socket number for the portal.

`PortalTag`

The portal group tag to which the portal belongs.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsimgt.h (include Iscsimgt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561559">ISCSI_PortalInfo WMI Class</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>