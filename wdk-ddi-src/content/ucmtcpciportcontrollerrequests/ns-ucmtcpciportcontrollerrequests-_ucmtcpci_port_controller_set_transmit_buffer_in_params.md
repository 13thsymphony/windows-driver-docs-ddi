---
UID : NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
title : _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
author : windows-driver-content
description : Stores the value of the TRANSMIT_BUFFER Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER request.
old-location : buses\ucmtcpci_port_controller_set_transmit_buffer_in_params.htm
old-project : usbref
ms.assetid : bcce81ce-7075-41a6-a8ab-95fe0f83436c
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure [Buses], buses.ucmtcpci_port_controller_set_transmit_buffer_in_params, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure pointer [Buses]
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
req.product : Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure
Stores the value of the TRANSMIT_BUFFER Register. This structure is used in the <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.

## Syntax
````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                   PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_TRANSMIT_BUFFER TransmitBuffer;
} UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS;
````

## Members


`PortControllerObject`

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.

`TransmitBuffer`

A pointer to the 
                     <b>UCMTCPCI_PORT_CONTROLLER_TRANSMIT_BUFFER</b> structure that contains 
                 the value to set in the TRANSMIT_BUFFER  Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>