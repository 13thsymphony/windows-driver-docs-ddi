---
UID : NS:wdfcompaniontarget._WDF_TASK_SEND_OPTIONS
title : _WDF_TASK_SEND_OPTIONS
author : windows-driver-content
description : For internal use only.
old-location : wdf\wdf_task_send_options.htm
old-project : wdf
ms.assetid : cb2fd11c-c6a5-4499-a340-f96ffcfbbe0f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_TASK_SEND_OPTIONS, PWDF_TASK_SEND_OPTIONS structure pointer, WDF_TASK_SEND_OPTIONS, wdfcompaniontarget/PWDF_TASK_SEND_OPTIONS, WDF_TASK_SEND_OPTIONS structure, wdf.wdf_task_send_options, PWDF_TASK_SEND_OPTIONS, wdfcompaniontarget/WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfcompaniontarget.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.23
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS
req.product : Windows 10 or later.
---

# _WDF_TASK_SEND_OPTIONS structure
For internal use only.

## Syntax
````
typedef struct _WDF_TASK_SEND_OPTIONS {
  ULONG    Size;
  ULONG    Flags;
  LONGLONG Timeout;
} WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS;
````

## Members


`Flags`



`Size`



`Timeout`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.23 |
| **Minimum UMDF version** |  |
| **Header** | wdfcompaniontarget.h |