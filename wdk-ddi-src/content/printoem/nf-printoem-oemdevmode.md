---
UID : NF:printoem.OEMDevMode
title : OEMDevMode function
author : windows-driver-content
description : OEMDevMode function
old-location : print\oemdevmode.htm
old-project : print
ms.assetid : 491217e9-8cc1-47de-af37-92db377a8c2d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print_obsoletefunctions_7a402f29-f8ab-48cc-951f-89b21f45aebd.xml, OEMDevMode, print.oemdevmode, OEMDevMode function [Print Devices], printoem/OEMDevMode
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : printoem.h
req.include-header : Printoem.h
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STDVARIABLEINDEX
req.product : Windows 10 or later.
---


# OEMDevMode function


## Syntax

````
BOOL APIENTRY OEMDevMode(
   DWORD       dwMode,
   POEMDMPARAM pOemDMParam
);
````

## Parameters

`dwMode`



`pOemDMParam`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |