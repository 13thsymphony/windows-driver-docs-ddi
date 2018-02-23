---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_IOCTL
title: "_UCMTCPCI_PORT_CONTROLLER_IOCTL"
author: windows-driver-content
description: Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.
old-location: buses\ucmtcpci_port_controller_ioctl.htm
old-project: UsbRef
ms.assetid: 61dcd4d9-cfd9-4878-96f5-c95465e0949e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, buses.ucmtcpci_port_controller_ioctl, UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration [Buses], ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, _UCMTCPCI_PORT_CONTROLLER_IOCTL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_IOCTL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, UCMTCPCI_PORT_CONTROLLER_IOCTL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	UcmTcpciPortControllerRequests.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_IOCTL
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_IOCTL Enumeration
Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.

## Syntax
````
typedef enum _UCMTCPCI_PORT_CONTROLLER_IOCTL { 
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS                      = = IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT                    = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER             = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT              = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT      = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO         = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED          = IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED           = IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED          = IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED  = IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED
} UCMTCPCI_PORT_CONTROLLER_IOCTL;
````

## Constants

<table>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_entered.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_exited.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</td>
                    <td>The  <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_message_header_info.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_receive_detect.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</td>
                    <td>The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</td>
                    <td>The  <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |