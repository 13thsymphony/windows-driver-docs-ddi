---
UID: NS:iscsiprf._MSiSCSI_QMIPSECStats
title: "_MSiSCSI_QMIPSECStats"
author: windows-driver-content
description: The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA.
old-location: storage\msiscsi_qmipsecstats.htm
old-project: storage
ms.assetid: 265ed956-1065-44be-ac8e-94bab2e4e8b8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats structure [Storage Devices], PMSiSCSI_QMIPSECStats, PMSiSCSI_QMIPSECStats structure pointer [Storage Devices], _MSiSCSI_QMIPSECStats, iscsiprf/MSiSCSI_QMIPSECStats, iscsiprf/PMSiSCSI_QMIPSECStats, storage.msiscsi_qmipsecstats, structs-iSCSI_979ce8ac-35be-4ac1-930a-6614053fc805.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
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
-	iscsiprf.h
api_name:
-	MSiSCSI_QMIPSECStats
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_QMIPSECStats, *PMSiSCSI_QMIPSECStats
---

# _MSiSCSI_QMIPSECStats structure
The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA.

## Syntax
```
typedef struct _MSiSCSI_QMIPSECStats {
  ULONGLONG ActiveSA;
  ULONGLONG PendingKeyOperations;
  ULONGLONG KeyAdditions;
  ULONGLONG KeyDeletions;
  ULONGLONG ReKeys;
  ULONGLONG ActiveTunnels;
  ULONGLONG BadSPIPackets;
  ULONGLONG PacketsNotDecrypted;
  ULONGLONG PacketsNotAuthenticated;
  ULONGLONG PacketsWithReplayDetection;
  ULONGLONG ConfidentialBytesSent;
  ULONGLONG ConfidentialBytesReceived;
  ULONGLONG AuthenticatedBytesSent;
  ULONGLONG AuthenticatedBytesReceived;
  ULONGLONG TransportBytesSent;
  ULONGLONG TransportBytesReceived;
  ULONGLONG TunnelBytesSent;
  ULONGLONG TunnelBytesReceived;
} *PMSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats;
```

## Members


`ActiveSA`

The number of active IPsec security associations (SAs).

`PendingKeyOperations`

The number of IPsec key operations that are in progress.

`KeyAdditions`

The number of successful IPsec SA negotiations.

`KeyDeletions`

The number of IPsec SA key deletions.

`ReKeys`

The number of re-key operations for IPsec SAs.

`ActiveTunnels`

The number of active IPsec tunnels.

`BadSPIPackets`

The number of packets for which the security parameters index (SPI) was incorrect.

`PacketsNotDecrypted`

The number of failed decryption packets.

`PacketsNotAuthenticated`

The number of packets for which data could not be verified.

`PacketsWithReplayDetection`

The number of packets that contained a valid sequence number field.

`ConfidentialBytesSent`

The number of bytes that are sent by using the encapsulating security payload (ESP) protocol.

`ConfidentialBytesReceived`

The number of bytes that are received by using the ESP protocol.

`AuthenticatedBytesSent`

The number of bytes that are sent by using the authentication header (AH) protocol.

`AuthenticatedBytesReceived`

The number of bytes that are received by using the AH protocol.

`TransportBytesSent`

The number of bytes that are sent by using the IPsec protocol.

`TransportBytesReceived`

The number of bytes that are received by using the IPsec protocol.

`TunnelBytesSent`

The number of bytes that are sent by using the IPsec tunnel mode.

`TunnelBytesReceived`

The number of bytes that are received by using the IPsec tunnel mode.

## Remarks
It is optional that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiprf.h (include Iscsiprf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563105">MSiSCSI_QMIPSECStats WMI Class</a>