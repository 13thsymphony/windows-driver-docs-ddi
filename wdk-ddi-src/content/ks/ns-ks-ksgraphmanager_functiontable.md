---
UID : NS:ks.KSGRAPHMANAGER_FUNCTIONTABLE
title : KSGRAPHMANAGER_FUNCTIONTABLE
author : windows-driver-content
description : .
old-location : stream\ksgraphmanager_functiontable.htm
old-project : stream
ms.assetid : F077B970-F146-43BC-BB92-A836C8843890
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKSGRAPHMANAGER_FUNCTIONTABLE, ks/PKSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE structure [Streaming Media Devices], ks/KSGRAPHMANAGER_FUNCTIONTABLE, stream.ksgraphmanager_functiontable, KSGRAPHMANAGER_FUNCTIONTABLE structure [Streaming Media Devices], KSGRAPHMANAGER_FUNCTIONTABLE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE
---

# KSGRAPHMANAGER_FUNCTIONTABLE structure


## Syntax
````
typedef struct _KSGRAPHMANAGER_FUNCTIONTABLE {
  PFNKSGRAPHMANAGER_NOTIFY NotifyEvent;
} KSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE;
````

## Members


`NotifyEvent`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |