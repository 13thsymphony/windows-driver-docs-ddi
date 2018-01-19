---
UID : NF:ntifs.IoCheckFunctionAccess
title : IoCheckFunctionAccess function
author : windows-driver-content
description : Reserved for system use.
old-location : ifsk\iocheckfunctionaccess.htm
old-project : ifsk
ms.assetid : 828a5197-eb2d-46d1-9853-0f8b4f288820
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IoCheckFunctionAccess
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoCheckFunctionAccess
req.alt-loc : ntifs.h
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
req.typenames : TOKEN_TYPE
---


# IoCheckFunctionAccess function
The <b>IoCheckFunctionAccess</b> routine is reserved for system use. See <a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>.

## Syntax

````
  IoCheckFunctionAccess(
    
);
````

## Parameters

`GrantedAccess`



`MajorFunction`



`MinorFunction`



`IoControlCode`



`Arg1`



`Arg2`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |