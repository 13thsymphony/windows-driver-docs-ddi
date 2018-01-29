---
UID : NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
title : EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
author : windows-driver-content
description : UCX invokes this callback to retrieve the host controller characteristics.
old-location : buses\evt_ucx_controller_get_transport_characteristics.htm
old-project : usbref
ms.assetid : 4394199C-6644-4E11-BDAF-625C2F94DEE8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.evt_ucx_controller_get_transport_characteristics, EvUcxControllerGetTransportCharacteristics callback function [Buses], EvUcxControllerGetTransportCharacteristics, EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, ucxcontroller/EvUcxControllerGetTransportCharacteristics, *PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function pointer [Buses], *PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ucxcontroller.h
req.include-header : Ucxclass.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
req.product : Windows 10 or later.
---


# EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS function
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

A pointer to a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_transport_characteristics.md">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that the client driver for the host controller fills with transport characteristics.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

This callback function is optional. Whenever transport characteristics change, the client driver is responsible for notifying UCX that one of the characteristics have changed using a new function <a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollernotifytransportcharacteristicschange.md">UcxControllerNotifyTransportCharacteristicsChange</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>