---
UID : NF:printoem.OEMCompression
title : OEMCompression function
author : windows-driver-content
description : OEMCompression function
old-location : print\oemcompression.htm
old-project : print
ms.assetid : e5246411-aa43-436f-b5e7-d7305ce659c9
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMCompression
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
req.alt-api : OEMCompression
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


# OEMCompression function


## Syntax

````
INT APIENTRY OEMCompression(
        PDEVOBJ                        pdevobj,
  _In_  _reads_bytes_(dwInLen) PBYTE   pInBuf,
  _Out_ _writes_bytes_(dwOutLen) PBYTE pOutBuf,
        DWORD                          dwInLen,
        DWORD                          dwOutLen
);
````

## Parameters

`pdevobj`



`pInBuf`



`pOutBuf`



`dwInLen`



`dwOutLen`




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