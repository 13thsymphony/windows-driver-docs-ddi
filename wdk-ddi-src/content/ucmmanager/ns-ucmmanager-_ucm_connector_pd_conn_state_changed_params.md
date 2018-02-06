---
UID: NS:ucmmanager._UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS
title: "_UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS"
author: windows-driver-content
description: Describes the parameters for PD connection changed event.
old-location: buses\ucm_connector_pd_conn_state_changed_params.htm
old-project: usbref
ms.assetid: 9D8A2B47-1677-4660-B006-CA0D5741FC05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucmmanager/UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, ucmmanager/PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, _UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure [Buses], PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, *PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure pointer [Buses], buses.ucm_connector_pd_conn_state_changed_params
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmmanager.h
apiname:
-	UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS"
req.product: Windows 10 or later.
---

# _UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure
Describes the parameters for PD connection changed event.

## Syntax
````
typedef struct _UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS {
  ULONG                      Size;
  UCM_PD_CONN_STATE          PdConnState;
  UCM_PD_REQUEST_DATA_OBJECT Rdo;
  UCM_CHARGING_STATE         ChargingState;
} UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS, *PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS;
````

## Members


`ChargingState`

Charging state of the port indicated by one of the <a href="..\ucmtypes\ne-ucmtypes-_ucm_charging_state.md">UCM_CHARGING_STATE</a>-typed flags.

`PdConnState`

The state of the connector indicated by one of the <a href="..\ucmtypes\ne-ucmtypes-_ucm_pd_conn_state.md">UCM_PD_CONN_STATE</a>-typed flags.

`Rdo`

An initialized <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_request_data_object.md">UCM_PD_REQUEST_DATA_OBJECT</a> structure that describes the characteristics of the new connection state.

`Size`

Size of the <b>UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</b> structure.

## Remarks
Initialize this structure by calling <a href="..\ucmmanager\nf-ucmmanager-ucm_connector_pd_conn_state_changed_params_init.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT</a>. An initialized <b>UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</b> structure is an input parameter value to <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a> that is used by the client driver to notify UcmCx about the Attached state of the port.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>