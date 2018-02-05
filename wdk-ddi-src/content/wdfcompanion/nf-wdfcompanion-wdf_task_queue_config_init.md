---
UID : NF:wdfcompanion.WDF_TASK_QUEUE_CONFIG_INIT
title : WDF_TASK_QUEUE_CONFIG_INIT function
author : windows-driver-content
description : For internal use only.
old-location : wdf\wdf_task_queue_config_init.htm
old-project : wdf
ms.assetid : 51c43509-074c-4118-afe5-2e568d733751
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdf_task_queue_config_init, wdfcompanion/WDF_TASK_QUEUE_CONFIG_INIT, WDF_TASK_QUEUE_CONFIG_INIT method, WDF_TASK_QUEUE_CONFIG_INIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfcompanion.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 2.23
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
req.typenames : WDF_TASK_QUEUE_DISPATCH_TYPE
req.product : Windows 10 or later.
---


# WDF_TASK_QUEUE_CONFIG_INIT function
For internal use only.

## Syntax

````
FORCEINLINE VOID WDF_TASK_QUEUE_CONFIG_INIT(
  _Out_ PWDF_TASK_QUEUE_CONFIG       Config,
  _In_  USHORT                       TaskQueueId,
  _In_  WDF_TASK_QUEUE_DISPATCH_TYPE DispatchType
);
````

## Parameters

`Config`



`TaskQueueId`



`DispatchType`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |
| **Library** | NtosKrnl.exe |