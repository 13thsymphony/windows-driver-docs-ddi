---
UID : NF:ucmmanager.UcmConnectorPowerDirectionChanged
title : UcmConnectorPowerDirectionChanged function
author : windows-driver-content
description : Notifies the USB connector manager framework extension (UcmCx) with the new power role of the partner connector.
old-location : buses\ucmconnectorpowerdirectionchanged.htm
old-project : usbref
ms.assetid : D1DB20DF-C0FD-4215-8227-CBBB18AF8BE3
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.ucmconnectorpowerdirectionchanged, UcmConnectorPowerDirectionChanged, ucmmanager/UcmConnectorPowerDirectionChanged, UcmConnectorPowerDirectionChanged method [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ucmmanager.h
req.include-header : Ucmcx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
req.umdf-ver : 2.15
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : UcmCxstub.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPORT_DATA_1, PORT_DATA_1"
req.product : Windows 10 or later.
---


# UcmConnectorPowerDirectionChanged function
Notifies the USB connector manager framework extension (UcmCx) with the new power role  of the partner connector.

## Syntax

````
NTSTATUS UcmConnectorPowerDirectionChanged(
  [in] UCMCONNECTOR    Connector,
  [in] BOOLEAN         Success,
  [in] UCM_POWER_ROLE  CurrentPowerRole
);
````

## Parameters

`Connector`

Handle to the connector object that the client driver received in the previous call to <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>.

`Success`

Used to indicate failure of a power-role swap that was initiated by UcmCx using <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_power_role.md">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>. 

If TRUE, the operation was successful. FALSE, otherwise.

`CurrentPowerRole`

One of the <a href="..\ucmtypes\ne-ucmtypes-_ucm_power_role.md">UCM_POWER_ROLE</a>-typed flags that indicates the new data role.


## Return Value

<b>UcmConnectorPowerDirectionChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value.

## Remarks

If the connector partner is attached, UcmCx updates the power role of the partner depending on the <i> CurrentPowerRole</i> value. 

UcmCx can change the power role of a connector, and invokes <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_power_role.md">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>. In response to that call, the client should perform the PR_Swap operation, and indicate success/failure of the operation by calling  <b>UcmConnectorPowerDirectionChanged</b>.

Alternatively, the client driver might choose to perform a role-swap autonomously, or the partner might perform a role-swap. In either case, when the role-swap has completed, the driver must report the new role to UcmCx using <b>UcmConnectorPowerDirectionChanged</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorPowerDirectionChanged method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>