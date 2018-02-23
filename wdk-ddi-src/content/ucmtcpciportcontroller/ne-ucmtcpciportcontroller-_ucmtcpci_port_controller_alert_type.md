---
UID: NE:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE"
author: windows-driver-content
description: Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.
old-location: buses\ucmtcpci_port_controller_alert_type.htm
old-project: UsbRef
ms.assetid: 77162a25-b5aa-45d0-ac4d-6500df9782de
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmHi, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmLo, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceivedHardReset, UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration [Buses], UcmTcpciPortControllerAlertVbusVoltageAlarmLo, UcmTcpciPortControllerAlertVbusVoltageAlarmHi, UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertRxBufferOverflow, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceiveSOPMessageStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertCCStatus, _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, ucmtcpciportcontroller/UcmTcpciPortControllerAlertInvalid, UcmTcpciPortControllerAlertFault, UcmTcpciPortControllerAlertCCStatus, UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UcmTcpciPortControllerAlertReceivedHardReset, ucmtcpciportcontroller/UcmTcpciPortControllerAlertPowerStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertFault, ucmtcpciportcontroller/UcmTcpciPortControllerAlertRxBufferOverflow, UcmTcpciPortControllerAlertInvalid, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageFailed, buses.ucmtcpci_port_controller_alert_type
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpciportcontroller.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE Enumeration
Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.

## Syntax
````
typedef enum _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE { 
  UcmTcpciPortControllerAlertInvalid                       = = 0x0,
  UcmTcpciPortControllerAlertCCStatus,
  UcmTcpciPortControllerAlertPowerStatus,
  UcmTcpciPortControllerAlertReceiveSOPMessageStatus,
  UcmTcpciPortControllerAlertReceivedHardReset,
  UcmTcpciPortControllerAlertTransmitSOPMessageFailed,
  UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded,
  UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful,
  UcmTcpciPortControllerAlertVbusVoltageAlarmHi,
  UcmTcpciPortControllerAlertVbusVoltageAlarmLo,
  UcmTcpciPortControllerAlertFault,
  UcmTcpciPortControllerAlertRxBufferOverflow,
  UcmTcpciPortControllerAlertVbusSinkDisconnectDetected
} UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertCCStatus</td>
                    <td>Indicates a
                        
                    CC status change alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertFault</td>
                    <td>Indicates that a Fault has occurred.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertInvalid</td>
                    <td>The alert is invalid.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertPowerStatus</td>
                    <td>Indicates a
                        
                    power status change alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertReceivedHardReset</td>
                    <td>Indicates a hard Reset alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertReceiveSOPMessageStatus</td>
                    <td>Indicates an SOP message alert.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertRxBufferOverflow</td>
                    <td>Indicates that the
                        
                     TCPC Rx buffer has overflowed.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded</td>
                    <td>Indicates that the
                        
                    SOP message transmission was not sent due to an incoming receive message.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageFailed</td>
                    <td>Indicates that the SOP message transmission was not successful.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful</td>
                    <td>Indicates that the SOP message transmission was successful.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusSinkDisconnectDetected</td>
                    <td>Indicates that a VBUS Sink Disconnect Threshold crossing has been detected</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusVoltageAlarmHi</td>
                    <td>Indicates a high-voltage alarm.</td>
                </tr>
            
                <tr>
                    <td>UcmTcpciPortControllerAlertVbusVoltageAlarmLo</td>
                    <td>Indicates a low-voltage alarm.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontroller.h |

## See Also

<a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>