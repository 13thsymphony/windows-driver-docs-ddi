---
UID: NS.UCXCONTROLLER._UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
title: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
author: windows-driver-content
description: Defines flags for the transport characteristics changes. This structure is used in the EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback function.
old-location: buses\ucx_controller_transport_characteristics_change_flags.htm
old-project: UsbRef
ms.assetid: B5D6BBE4-2FFF-41CB-B747-AA3C6CE9064E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.alt-loc: UcxController.h
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
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS structure



## -description
Defines flags for the transport characteristics changes. This structure is used in the <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_set_transport_characteristics_change_notification.md">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> callback function.



## -syntax

````
typedef union _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS {
  ULONG AsUlong32;
  struct {
    ULONG                     CurrentRoundtripLatencyChanged  :1;
    ULONG                     CurrentTotalBandwidthChanged  :1;
  };
} UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, *PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS;
````


## -struct-fields

### -field AsUlong32

Reserved.


### -field                     CurrentRoundtripLatencyChanged

Contains the current round-trip delay in milliseconds from the time a non-isochronous transfer is received by the USB driver stack to the time that the transfer is completed.  

For MA-USB, the underlying network could be WiFi, WiGig, Ethernet etc. The delay can vary depending on the underlying network conditions. A client driver should query the latency periodically or whenever it is notified of a change. 



### -field                     CurrentTotalBandwidthChanged

Contains the total bandwidth of the host controller’s shared transport. 

For MA-USB, the underlying network transport could be WiFi, WiGig, Ethernet etc. The total available bandwidth can vary depending on several factors such as the negotiation WiFi channel. A client driver should query the total bandwidth periodically or whenever it is notified of a change. 



## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UcxController.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_set_transport_characteristics_change_notification.md">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

