---
UID: NS.ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
title: UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
author: windows-driver-content
description: Stores the value of the VBUS_VOLTAGE_ALARM_LO_CFG Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO request.
old-location: buses\ucmtcpci_port_controller_set_message_header_info_in_params.htm
ms.assetid: 1efccde1-1e96-4a38-aa5a-5b386ad10e51
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: usbref
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
req.alt-loc: UcmTcpciPortControllerRequests.h
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
ms.keywords: UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
req.iface: 
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure



## -description
<p>
             Stores the value of the VBUS_VOLTAGE_ALARM_LO_CFG Register. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805837">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.
                 </p>


## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                       PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_MESSAGE_HEADER_INFO MessageHeaderInfo;
} UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS;
````


## -struct-fields
<dl>

### -field <b>PortControllerObject</b>

<dd>
<p>Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.</p>
</dd>

### -field <b>MessageHeaderInfo</b>

<dd>
<p>
                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_MESSAGE_HEADER_INFO</b> structure that describes the MESSAGE_HEADER_INFO Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>UcmTcpciPortControllerRequests.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt805837">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
