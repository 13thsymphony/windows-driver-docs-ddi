---
UID: NS.UCMTCPCIPORTCONTROLLERREQUESTS._UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
author: windows-driver-content
description: Stores the values of all control registers. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_set_control_in_params.htm
old-project: usbref
ms.assetid: d81d76a9-e482-4e22-93c0-a320905ee203
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
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
req.alt-api: UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
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
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure



## -description

             Stores the values of all control registers. This structure is used in the <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.


## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_CONTROL_TYPE ControlType;
  union {
    UCMTCPCI_PORT_CONTROLLER_TCPC_CONTROL  TCPCControl;
    UCMTCPCI_PORT_CONTROLLER_ROLE_CONTROL  RoleControl;
    UCMTCPCI_PORT_CONTROLLER_FAULT_CONTROL FaultControl;
    UCMTCPCI_PORT_CONTROLLER_POWER_CONTROL PowerControl;
  };
} UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS;
````


## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="buses.ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.

### -field ControlType


                     A <b>UCMTCPCI_PORT_CONTROLLER_CONTROL_TYPE</b>-value that 
                 indicates the type of control register. This enumeration is declared in UcmTcpciSpec.h.

### -field TCPCControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_TCPC_CONTROL</b> structure that describes the TCPC_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

### -field RoleControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_ROLE_CONTROL</b> structure that describes the ROLE_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

### -field FaultControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_FAULT_CONTROL</b> structure that describes the FAULT_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

### -field PowerControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_POWER_CONTROL</b> structure that describes the FAULT_POWER Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucmtcpciportcontrollerrequests.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
