---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_IOCTL
title: "_UCMTCPCI_PORT_CONTROLLER_IOCTL"
author: windows-driver-content
description: Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.
old-location: buses\ucmtcpci_port_controller_ioctl.htm
old-project: usbref
ms.assetid: 61dcd4d9-cfd9-4878-96f5-c95465e0949e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IOCTL, UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration [Buses], _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER, _UCMTCPCI_PORT_CONTROLLER_IOCTL, buses.ucmtcpci_port_controller_ioctl, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_IOCTL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UcmTcpciPortControllerRequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_IOCTL
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_IOCTL Enumeration
Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.

## Syntax
```
typedef enum _UCMTCPCI_PORT_CONTROLLER_IOCTL {
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS                              ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL                             ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL                             ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT                            ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER                     ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT                      ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT              ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND                             ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO                 ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED                  ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED                   ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED                  ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED          ,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED
} UCMTCPCI_PORT_CONTROLLER_IOCTL;
```

## Constants

<table>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805833">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805832">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805836">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805839">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</td>
                    <td>The  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805840">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805838">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805835">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805834">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805837">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805828">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805829">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/mt805830">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</td>
                    <td>The  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805831">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a> request.</td>
                </tr>
            
                <tr>
                    <td>_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |