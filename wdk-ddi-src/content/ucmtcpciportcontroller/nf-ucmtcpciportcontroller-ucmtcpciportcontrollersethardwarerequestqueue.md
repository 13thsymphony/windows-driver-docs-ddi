---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerSetHardwareRequestQueue
title: UcmTcpciPortControllerSetHardwareRequestQueue function
author: windows-driver-content
description: Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.
old-location: buses\ucmtcpciportcontrollersethardwarerequestqueue.htm
old-project: usbref
ms.assetid: 47142adb-4d22-41eb-b455-93409bbffffb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcmTcpciPortControllerSetHardwareRequestQueue, UcmTcpciPortControllerSetHardwareRequestQueue method [Buses], buses.ucmtcpciportcontrollersethardwarerequestqueue, ucmtcpciportcontroller/UcmTcpciPortControllerSetHardwareRequestQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UcmTcpciPortControllerSetHardwareRequestQueue
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---


# UcmTcpciPortControllerSetHardwareRequestQueue function
Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.

## Syntax

````
VOID UcmTcpciPortControllerSetHardwareRequestQueue(
   UCMTCPCIPORTCONTROLLER PortControllerObject,
   WDFQUEUE               HardwareRequestQueue
);
````

## Parameters

`PortControllerObject`

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.

`HardwareRequestQueue`

A handle to the framework queue object to assign.


## Return Value

This method does not return a value.

## Remarks

The client driver must call <b>UcmTcpciPortControllerSetHardwareRequestQueue</b> after creating the port controller object. The driver must call this method only once before calling <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md">UcmTcpciPortControllerStart</a>.

The parent of the queue object is the port controller object. 


A client driver may choose to use the same queue across multiple port controller objects. However, in that case the driver must make sure that the port controller objects do not outlive the queue object. The queue object must be deleted only after all the port controllers have been stopped. UcmTcpciCx guarantees  that only one request is processed in the queue at a time per port controller object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ucmtcpciportcontroller.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>