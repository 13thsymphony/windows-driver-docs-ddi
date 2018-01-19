---
UID : NF:winspool.FreePrintNamedPropertyArray
title : FreePrintNamedPropertyArray function
author : windows-driver-content
description : .
old-location : print\freeprintnamedpropertyarray.htm
old-project : print
ms.assetid : 18E24562-F57A-492F-9254-722ABA0B2BC4
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : FreePrintNamedPropertyArray
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winspool.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FreePrintNamedPropertyArray
req.alt-loc : Winspool.h
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
req.typenames : BIDI_TYPE
req.product : Windows 10 or later.
---


# FreePrintNamedPropertyArray function


## Syntax

````
void WINAPI FreePrintNamedPropertyArray(
  _In_        DWORD               cProperties,
  _Inout_opt_ PrintNamedProperty  **ppProperties
);
````

## Parameters

`cProperties`



`ppProperties`




## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winspool.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |