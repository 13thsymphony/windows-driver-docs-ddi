---
UID : NS:winspool.PrintPropertyValue
title : PrintPropertyValue
author : windows-driver-content
description : .
old-location : print\printpropertyvalue.htm
old-project : print
ms.assetid : B442AE8E-A4CE-481A-A69C-496CBF3E4722
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PrintPropertyValue, PrintPropertyValue structure [Print Devices], winspool/PrintPropertyValue, print.printpropertyvalue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : winspool.h
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
req.typenames : PrintPropertyValue
req.product : Windows 10 or later.
---

# PrintPropertyValue structure


## Syntax
````
typedef struct {
  EPrintPropertyType ePropertyType;
  union {
    BYTE     propertyByte;
    PWSTR    propertyString;
    LONG     propertyInt32;
    LONGLONG propertyInt64;
    struct {
      DWORD  cbBuf;
      LPVOID pBuf;
    } propertyBlob;
  } value;
} PrintPropertyValue;
````

## Members


`ePropertyType`



`value`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winspool.h |