---
UID: NS.ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
title: UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
author: windows-driver-content
description: Stores the value of the RECEIVE_DETECT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT request.
old-location: buses\ucmtcpci_port_controller_set_receive_detect_in_params.htm
old-project: usbref
ms.assetid: 2a33613b-e3f5-47e0-b05e-0427a0fb3c58
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
req.alt-loc: Ucmtcpciportcontrollerrequests.h
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
req.iface: 
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS structure



## -description
<p>
             Stores the value of the RECEIVE_DETECT Register. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805838">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.
                 </p>


## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                  PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_RECEIVE_DETECT ReceiveDetect;
} UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS;
````


## -struct-fields
<dl>

### -field <b>PortControllerObject</b>

<dd>
<p>Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.</p>
</dd>

### -field <b>ReceiveDetect</b>

<dd>
<p>
                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_RECEIVE_DETECT</b> structure that describes the RECEIVE_DETECT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.</p>
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
<dt>Ucmtcpciportcontrollerrequests.h</dt>
</dl>
</td>
</tr>
</table>