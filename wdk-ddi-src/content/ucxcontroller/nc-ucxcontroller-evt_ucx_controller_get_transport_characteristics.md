---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
title: EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
author: windows-driver-content
description: UCX invokes this callback to retrieve the host controller characteristics.
old-location: buses\evt_ucx_controller_get_transport_characteristics.htm
old-project: usbref
ms.assetid: 4394199C-6644-4E11-BDAF-625C2F94DEE8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, *PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function pointer [Buses], EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, EvUcxControllerGetTransportCharacteristics, EvUcxControllerGetTransportCharacteristics callback function [Buses], buses.evt_ucx_controller_get_transport_characteristics, ucxcontroller/EvUcxControllerGetTransportCharacteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	UserDefined
api_location:
-	UcxController.h
api_name:
-	*PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
req.product: Windows 10 or later.
---


# EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function
UCX invokes this callback to retrieve the host controller characteristics.

## Syntax

```
EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS EvtUcxControllerGetTransportCharacteristics;

_IRQL_requires_same_ NTSTATUS EvtUcxControllerGetTransportCharacteristics(
  UCXCONTROLLER UcxController,
  PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS UcxControllerTransportCharacteristics
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`UcxControllerTransportCharacteristics`

A pointer to a <a href="https://msdn.microsoft.com/9F267427-8D70-45D5-A8E6-67A1C6B73CDB">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that the client driver for the host controller fills with transport characteristics.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

This callback function is optional. Whenever transport characteristics change, the client driver is responsible for notifying UCX that one of the characteristics have changed using a new function <a href="https://msdn.microsoft.com/DB49DF98-8A5B-4528-B312-63CE3DFABEF2">UcxControllerNotifyTransportCharacteristicsChange</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>