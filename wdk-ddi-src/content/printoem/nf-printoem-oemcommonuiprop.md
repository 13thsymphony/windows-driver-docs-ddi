---
UID : NF:printoem.OEMCommonUIProp
title : OEMCommonUIProp function
author : windows-driver-content
description : OEMCommonUIProp function
old-location : print\oemcommonuiprop.htm
old-project : print
ms.assetid : d993117d-e8d4-4e00-bcb8-c83a15b6c037
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : OEMCommonUIProp, print_obsoletefunctions_ef86ce33-1102-4045-b3ad-bba26bafd3de.xml, print.oemcommonuiprop, OEMCommonUIProp function [Print Devices], printoem/OEMCommonUIProp
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


# OEMCommonUIProp function


## Syntax

````
BOOL APIENTRY OEMCommonUIProp(
   DWORD         dwMode,
   POEMCUIPPARAM pOemCUIPParam
);
````

## Parameters

`dwMode`



`pOemCUIPParam`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printoem.h (include Printoem.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |