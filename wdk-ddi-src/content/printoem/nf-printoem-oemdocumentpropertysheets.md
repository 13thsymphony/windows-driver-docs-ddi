---
UID : NF:printoem.OEMDocumentPropertySheets
title : OEMDocumentPropertySheets function
author : windows-driver-content
description : OEMDocumentPropertySheets function
old-location : print\oemdocumentpropertysheets.htm
old-project : print
ms.assetid : 81c5eced-3d68-4202-83b9-57d661fe4952
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMDocumentPropertySheets
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
req.alt-api : OEMDocumentPropertySheets
req.alt-loc : printoem.h
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
req.typenames : STDVARIABLEINDEX
req.product : Windows 10 or later.
---


# OEMDocumentPropertySheets function


## Syntax

````
LRESULT APIENTRY OEMDocumentPropertySheets(
  _In_ PPROPSHEETUI_INFO pPSUIInfo,
       LPARAM            lParam
);
````

## Parameters

`pPSUIInfo`



`lParam`




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