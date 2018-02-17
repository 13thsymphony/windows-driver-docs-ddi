---
UID: NF:ucxcontroller.UcxControllerNotifyTransportCharacteristicsChange
title: UcxControllerNotifyTransportCharacteristicsChange function
author: windows-driver-content
description: Notifies UCX about a new port change event from host controller.
old-location: buses\ucxcontrollernotifytransportcharacteristicschange.htm
old-project: usbref
ms.assetid: DB49DF98-8A5B-4528-B312-63CE3DFABEF2
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ucxcontrollernotifytransportcharacteristicschange, UcxControllerNotifyTransportCharacteristicsChange function [Buses], ucxcontroller/UcxControllerNotifyTransportCharacteristicsChange, UcxControllerNotifyTransportCharacteristicsChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Ucxstubs.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ucxstubs.lib
-	Ucxstubs.dll
apiname:
-	UcxControllerNotifyTransportCharacteristicsChange
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---


# UcxControllerNotifyTransportCharacteristicsChange function
Notifies UCX about a new port change event from host controller.

## Syntax

````
void UcxControllerNotifyTransportCharacteristicsChange(
  _In_  UCXCONTROLLER                             UcxController,
  _Out_ PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS UcxControllerTransportCharacteristics
);
````

## Parameters

`Controller`

TBD

`UcxControllerTransportCharacteristics`

A pointer to a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_transport_characteristics.md">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that contains the updated transport characteristics.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **Library** | Ucxstubs.lib |

## See Also

<a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics.md">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxControllerNotifyTransportCharacteristicsChange function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>