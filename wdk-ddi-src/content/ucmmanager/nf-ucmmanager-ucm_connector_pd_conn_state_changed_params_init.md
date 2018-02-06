---
UID: NF:ucmmanager.UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
title: UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure.
old-location: buses\ucm_connector_pd_conn_state_changed_params_init.htm
old-project: usbref
ms.assetid: 177AF27E-3EBA-4D43-BAF2-11834784F762
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucmmanager/UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT, buses.ucm_connector_pd_conn_state_changed_params_init, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
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
-	UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function
Initializes a <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure.

## Syntax

````
void UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT(
  _Out_ PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS Params,
  _In_  UCM_PD_CONN_STATE                           PdConnState
);
````

## Parameters

`Params`

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure to initialize.

`PdConnState`

A <a href="..\ucmtypes\ne-ucmtypes-_ucm_pd_conn_state.md">UCM_PD_CONN_STATE</a>-typed flag that indicates the connection state of the partner port.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>