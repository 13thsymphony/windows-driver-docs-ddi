---
UID : NS:ks.KSE_PIN
title : KSE_PIN
author : windows-driver-content
description : "."
old-location : stream\kse_pin.htm
old-project : stream
ms.assetid : 6936F732-ECAA-4CA7-B2AF-CA22A5C93FC9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : "*PKSE_PIN, ks/PKSE_PIN, KSE_PIN structure [Streaming Media Devices], KSE_PIN, PKSE_PIN structure pointer [Streaming Media Devices], stream.kse_pin, PKSE_PIN, ks/KSE_PIN"
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
req.typenames : "*PKSE_PIN, KSE_PIN"
---

# KSE_PIN structure


## Syntax
````
typedef struct {
  ULONG Event;
  ULONG PinId;
  ULONG Reserved;
} KSE_PIN, *PKSE_PIN;
````

## Members


`Event`



`PinId`



`Reserved`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |