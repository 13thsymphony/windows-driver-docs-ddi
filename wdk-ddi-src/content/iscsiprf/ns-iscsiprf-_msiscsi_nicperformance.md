---
UID: NS:iscsiprf._MSiSCSI_NICPerformance
title: _MSiSCSI_NICPerformance
author: windows-driver-content
description: The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port.
old-location: storage\msiscsi_nicperformance.htm
old-project: storage
ms.assetid: 921e6e44-adc2-4257-b11e-941121f5bfd7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance, MSiSCSI_NICPerformance
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
req.alt-api: MSiSCSI_NICPerformance
req.alt-loc: iscsiprf.h
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
req.typenames: *PMSiSCSI_NICPerformance, MSiSCSI_NICPerformance
---

# _MSiSCSI_NICPerformance structure



## -description
The MSiSCSI_NICPerformance structure can be used by an iSCSI initiator to report statistics for a network interface card (NIC) port. 



## -syntax

````
typedef struct _MSiSCSI_NICPerformance {
  ULONG BytesTransmitted;
  ULONG BytesReceived;
  ULONG PDUTransmitted;
  ULONG PDUReceived;
} MSiSCSI_NICPerformance, *PMSiSCSI_NICPerformance;
````


## -struct-fields

### -field BytesTransmitted

The number of bytes that are transmitted through the Ethernet port.


### -field BytesReceived

The number of bytes that are received through the Ethernet port.


### -field PDUTransmitted

The number of PDUs that are transmitted through the Ethernet port.


### -field PDUReceived

The number of PDUs that are received through the Ethernet port.


## -remarks
It is optional that you implement this class.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiprf.h (include Iscsiprf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563089">MSiSCSI_NICPerformance WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_NICPerformance structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

