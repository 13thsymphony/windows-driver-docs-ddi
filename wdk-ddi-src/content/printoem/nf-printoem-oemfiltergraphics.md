---
UID : NF:printoem.OEMFilterGraphics
title : OEMFilterGraphics function
author : windows-driver-content
description : OEMFilterGraphics function
old-location : print\oemfiltergraphics.htm
old-project : print
ms.assetid : 1b81de5a-440a-4209-992e-7f79c047245c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : OEMFilterGraphics function [Print Devices], print_obsoletefunctions_fa20bac8-85b3-4ddb-8bf6-1a659f30b3ad.xml, OEMFilterGraphics, print.oemfiltergraphics, printoem/OEMFilterGraphics
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


# OEMFilterGraphics function


## Syntax

````
BOOL APIENTRY OEMFilterGraphics(
       PDEVOBJ                    pdevobj,
  _In_ _reads_bytes_(dwLen) PBYTE pBuf,
       DWORD                      dwLen
);
````

## Parameters

`pdevobj`



`pBuf`



`dwLen`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |