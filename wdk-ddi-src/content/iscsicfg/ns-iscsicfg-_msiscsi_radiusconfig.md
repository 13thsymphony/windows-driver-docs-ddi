---
UID: NS:iscsicfg._MSiSCSI_RADIUSConfig
title: "_MSiSCSI_RADIUSConfig"
author: windows-driver-content
description: The MSiSCSI_RADIUSConfig structure provides information that the initiator requires to use the remote authentication dial-in user service (RADIUS).
old-location: storage\msiscsi_radiusconfig.htm
old-project: storage
ms.assetid: 6f8be86e-2729-4aa9-982d-df323f05cf1c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMSiSCSI_RADIUSConfig, MSiSCSI_RADIUSConfig, MSiSCSI_RADIUSConfig structure [Storage Devices], PMSiSCSI_RADIUSConfig, PMSiSCSI_RADIUSConfig structure pointer [Storage Devices], _MSiSCSI_RADIUSConfig, iscsicfg/MSiSCSI_RADIUSConfig, iscsicfg/PMSiSCSI_RADIUSConfig, storage.msiscsi_radiusconfig, structs-iSCSI_9f8461c3-b370-4aed-a5a5-58f9dd276944.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
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
-	iscsicfg.h
api_name:
-	MSiSCSI_RADIUSConfig
product: Windows
targetos: Windows
req.typenames: MSiSCSI_RADIUSConfig, *PMSiSCSI_RADIUSConfig
---

# _MSiSCSI_RADIUSConfig structure
The MSiSCSI_RADIUSConfig structure provides information that the initiator requires to use the remote authentication dial-in user service (RADIUS).

## Syntax
````
typedef struct _MSiSCSI_RADIUSConfig {
  BOOLEAN          UseRADIUSForCHAP;
  ULONG            SharedSecretSizeInBytes;
  ISCSI_IP_Address RADIUSServer;
  ISCSI_IP_Address BackupRADIUSServer;
  ULONG            Reserved;
  UCHAR            SharedSecret[1];
} MSiSCSI_RADIUSConfig, *PMSiSCSI_RADIUSConfig;
````

## Members


`BackupRADIUSServer`

A ISCSI_IP_Address structure that specifies a fixed addresses for a backup RADIUS server.

`RADIUSServer`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that specifies a fixed address for the RADIUS server. The ISCSI_IP_Address structure defines the IP address in a way that is independent of the version of the IP protocol in use.

`Reserved`

Reserved for Microsoft use only. Set this member to zero.

`SharedSecret`

A variable-length array that contains a shared secret. The initiator uses this shared secret to authenticate primary and backup RADIUS servers.

`SharedSecretSizeInBytes`

The size, in bytes, of shared secret for use with RADIUS servers.

`UseRADIUSForCHAP`

A Boolean value that indicates whether the initiator should use RADIUS for authentication during the challenge handshake of the challenge handshake authentication protocol (CHAP). If this member is <b>TRUE</b>, the initiator should use RADIUS for authentication during the challenge handshake of CHAP. If this member is <b>FALSE</b>, the initiator is not required to use RADIUS.

## Remarks
Initiators use RADIUS servers to perform authentication during the challenge handshake of CHAP.

The WMI tool suite automatically generates a declaration of the MSiSCSI_RADIUSConfig structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563114">MSiSCSI_RADIUSConfig WMI Class</a> in <i>Config.mof</i>. 

Initiators that support using RADIUS for CHAP authentication must implement the MSiSCSI_RADIUSConfig class.

Initiators should use RADIUS whenever possible, because RADIUS allows the centralized management of CHAP credentials. 

Initiators should register each instance of the MSiSCSI_RADIUSConfig class using the name of the physical device object (PDO) for the HBAYou must implement this class if the adapter supports authentication via RADIUS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsicfg.h (include Iscsicfg.h) |

## See Also

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563114">MSiSCSI_RADIUSConfig WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_RADIUSConfig structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>