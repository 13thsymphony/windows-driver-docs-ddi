---
UID : NF:d3dkmthk.D3DKMTSubmitCommandToHwQueue
title : D3DKMTSubmitCommandToHwQueue function
author : windows-driver-content
description : Used to submit a command to the hardware queue.
old-location : display\d3dkmtsubmitcommandtohwqueue.htm
old-project : display
ms.assetid : E4E6B637-BFAF-4ACD-86C2-109704B8D33D
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTSubmitCommandToHwQueue, D3DKMTSubmitCommandToHwQueue function [Display Devices], d3dkmthk/D3DKMTSubmitCommandToHwQueue, display.d3dkmtsubmitcommandtohwqueue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Tbd
req.dll : Tbd
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTSubmitCommandToHwQueue function
Used to submit a command to the hardware queue.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSubmitCommandToHwQueue(
  _In_ const D3DKMT_SUBMITCOMMANDTOHWQUEUE *submitCommandToHwQueue
);
````

## Parameters

`D3DKMT_SUBMITCOMMANDTOHWQUEUE`

TBD


## Return Value

Returns STATUS_SUCCESS if called successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |