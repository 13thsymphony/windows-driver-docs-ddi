---
UID : NE:ks.KSPROPERTY_GENERAL
title : KSPROPERTY_GENERAL
author : windows-driver-content
description : .
old-location : stream\ksproperty_general.htm
old-project : stream
ms.assetid : 45D94211-4756-4D3C-8512-2AF7953CFADC
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_GENERAL enumeration [Streaming Media Devices], KSPROPERTY_GENERAL, KSPROPERTY_GENERAL_COMPONENTID, stream.ksproperty_general, ks/KSPROPERTY_GENERAL, ks/KSPROPERTY_GENERAL_COMPONENTID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
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
req.typenames : KSPROPERTY_GENERAL
---

# KSPROPERTY_GENERAL Enumeration


## Syntax
````
typedef enum  { 
  KSPROPERTY_GENERAL_COMPONENTID
} KSPROPERTY_GENERAL;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_GENERAL_COMPONENTID</td>
<td>Specify to access general component information stored in the <b>KSCOMPONENTID</b> structure.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |