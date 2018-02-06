---
UID: NS:iscsiprf._MSiSCSI_NICPerformance
title: "_MSiSCSI_NICPerformance"
author: windows-driver-content
description: The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port.
old-location: storage\msiscsi_nicperformance.htm
old-project: storage
ms.assetid: 921e6e44-adc2-4257-b11e-941121f5bfd7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.msiscsi_nicperformance, PMSiSCSI_NICPerformance structure pointer [Storage Devices], MSiSCSI_NICPerformance structure [Storage Devices], _MSiSCSI_NICPerformance, iscsiprf/MSiSCSI_NICPerformance, iscsiprf/PMSiSCSI_NICPerformance, PMSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance, structs-iSCSI_a4d4dddd-24f6-4aa5-9b2c-61c0f1604fdb.xml, MSiSCSI_NICPerformance
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiprf.h
apiname:
-	MSiSCSI_NICPerformance
product: Windows
targetos: Windows
req.typenames: MSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance
---

# _MSiSCSI_NICPerformance structure
The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port.

## Syntax
````
typedef struct _MSiSCSI_NICPerformance {
  ULONG BytesTransmitted;
  ULONG BytesReceived;
  ULONG PDUTransmitted;
  ULONG PDUReceived;
} MSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance;
````

## Members


`BytesReceived`

The number of bytes that are received through the Ethernet port.

`BytesTransmitted`

The number of bytes that are transmitted through the Ethernet port.

`PDUReceived`

The number of PDUs that are received through the Ethernet port.

`PDUTransmitted`

The number of PDUs that are transmitted through the Ethernet port.

## Remarks
It is optional that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiprf.h (include Iscsiprf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563089">MSiSCSI_NICPerformance WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_NICPerformance structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>