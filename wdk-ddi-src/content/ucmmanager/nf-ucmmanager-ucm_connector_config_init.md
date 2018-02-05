---
UID : NF:ucmmanager.UCM_CONNECTOR_CONFIG_INIT
title : UCM_CONNECTOR_CONFIG_INIT function
author : windows-driver-content
description : Initializes a UCM_CONNECTOR_CONFIG structure.
old-location : buses\ucm_connector_config_init.htm
old-project : usbref
ms.assetid : F9076ED0-A9D2-441A-A084-941C05EF9CCA
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ucmmanager/UCM_CONNECTOR_CONFIG_INIT, buses.ucm_connector_config_init, UCM_CONNECTOR_CONFIG_INIT, UCM_CONNECTOR_CONFIG_INIT function [Buses]
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPORT_DATA_1, PORT_DATA_1"
req.product : Windows 10 or later.
---


# UCM_CONNECTOR_CONFIG_INIT function
Initializes a <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_config.md">UCM_CONNECTOR_CONFIG</a> structure.

## Syntax

````
FORCEINLINE void UCM_CONNECTOR_CONFIG_INIT(
  _Out_ PUCM_CONNECTOR_CONFIG  Config,
  _In_  ULONGULONG             ConnectorId
);
````

## Parameters

`Config`

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_config.md">UCM_CONNECTOR_CONFIG</a> structure to initialize.

`ConnectorId`

The identifier to assign to the connector object. If there is only one connector, pass 0.


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

<a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_CONFIG_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>