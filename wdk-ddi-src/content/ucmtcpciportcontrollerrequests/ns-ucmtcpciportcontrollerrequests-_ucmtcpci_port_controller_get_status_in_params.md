---
UID: NS.UCMTCPCIPORTCONTROLLERREQUESTS._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
author: windows-driver-content
description: This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location: buses\ucmtcpci_port_controller_get_status_in_params.htm
old-project: usbref
ms.assetid: 1b57413b-e1cf-4ec4-80f4-aedffc015b46
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
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
req.alt-api: UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
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
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure



## -description

             
             This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>  request.
         





## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER PortControllerObject;
} UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS;
````


## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UcmTcpciPortControllerRequests.h</dt>
</dl>
</td>
</tr>
</table>