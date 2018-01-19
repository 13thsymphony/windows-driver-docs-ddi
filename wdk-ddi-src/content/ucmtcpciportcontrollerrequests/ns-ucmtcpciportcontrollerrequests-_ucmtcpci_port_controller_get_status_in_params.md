---
UID : NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
title : _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
author : windows-driver-content
description : This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location : buses\ucmtcpci_port_controller_get_status_in_params.htm
old-project : usbref
ms.assetid : 1b57413b-e1cf-4ec4-80f4-aedffc015b46
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ucmtcpciportcontrollerrequests.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
req.alt-loc : UcmTcpciPortControllerRequests.h
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
req.typenames : "*PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS"
req.product : Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure
This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>  request.

## Syntax
````
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER PortControllerObject;
} UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS;
````

## Members

        
            `PortControllerObject`

            Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ucmtcpciportcontrollerrequests.h |