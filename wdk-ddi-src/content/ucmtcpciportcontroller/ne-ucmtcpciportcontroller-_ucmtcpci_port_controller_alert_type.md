---
UID: NE:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE"
author: windows-driver-content
description: Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.
old-location: buses\ucmtcpci_port_controller_alert_type.htm
old-project: usbref
ms.assetid: 77162a25-b5aa-45d0-ac4d-6500df9782de
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration [Buses], UcmTcpciPortControllerAlertCCStatus, UcmTcpciPortControllerAlertFault, UcmTcpciPortControllerAlertInvalid, UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UcmTcpciPortControllerAlertReceivedHardReset, UcmTcpciPortControllerAlertRxBufferOverflow, UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, UcmTcpciPortControllerAlertVbusVoltageAlarmHi, UcmTcpciPortControllerAlertVbusVoltageAlarmLo, _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, buses.ucmtcpci_port_controller_alert_type, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertCCStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertFault, ucmtcpciportcontroller/UcmTcpciPortControllerAlertInvalid, ucmtcpciportcontroller/UcmTcpciPortControllerAlertPowerStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceiveSOPMessageStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceivedHardReset, ucmtcpciportcontroller/UcmTcpciPortControllerAlertRxBufferOverflow, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageFailed, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmHi, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmLo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtcpciportcontroller.h
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
-	ucmtcpciportcontroller.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE Enumeration
Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.

## Syntax
```
typedef enum _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE {
  UcmTcpciPortControllerAlertInvalid                       ,
  UcmTcpciPortControllerAlertCCStatus                      ,
  UcmTcpciPortControllerAlertPowerStatus                   ,
  UcmTcpciPortControllerAlertReceiveSOPMessageStatus       ,
  UcmTcpciPortControllerAlertReceivedHardReset             ,
  UcmTcpciPortControllerAlertTransmitSOPMessageFailed      ,
  UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded   ,
  UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful  ,
  UcmTcpciPortControllerAlertVbusVoltageAlarmHi            ,
  UcmTcpciPortControllerAlertVbusVoltageAlarmLo            ,
  UcmTcpciPortControllerAlertFault                         ,
  UcmTcpciPortControllerAlertRxBufferOverflow              ,
  UcmTcpciPortControllerAlertVbusSinkDisconnectDetected
} UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertInvalid</td>
                    <td>The alert is invalid.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertCCStatus</td>
                    <td>Indicates a
                        
                    CC status change alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertPowerStatus</td>
                    <td>Indicates a
                        
                    power status change alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertReceiveSOPMessageStatus</td>
                    <td>Indicates an SOP message alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertReceivedHardReset</td>
                    <td>Indicates a hard Reset alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageFailed</td>
                    <td>Indicates that the SOP message transmission was not successful.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded</td>
                    <td>Indicates that the
                        
                    SOP message transmission was not sent due to an incoming receive message.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful</td>
                    <td>Indicates that the SOP message transmission was successful.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusVoltageAlarmHi</td>
                    <td>Indicates a high-voltage alarm.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusVoltageAlarmLo</td>
                    <td>Indicates a low-voltage alarm.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertFault</td>
                    <td>Indicates that a Fault has occurred.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertRxBufferOverflow</td>
                    <td>Indicates that the
                        
                     TCPC Rx buffer has overflowed.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusSinkDisconnectDetected</td>
                    <td>Indicates that a VBUS Sink Disconnect Threshold crossing has been detected</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontroller.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt805898">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a>