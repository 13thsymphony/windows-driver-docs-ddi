---
UID : NS:ntifs.__PUBLIC_OBJECT_TYPE_INFORMATION
title : "__PUBLIC_OBJECT_TYPE_INFORMATION"
author : windows-driver-content
description : The PUBLIC_OBJECT_TYPE_INFORMATION structure holds the type name of the object.
old-location : ifsk\public_object_type_information.htm
old-project : ifsk
ms.assetid : 7b80c3df-befe-4648-ab61-78cfb8d4b7ef
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ntifs/PUBLIC_OBJECT_TYPE_INFORMATION, PUBLIC_OBJECT_TYPE_INFORMATION structure [Installable File System Drivers], ifsk.public_object_type_information, PUBLIC_OBJECT_TYPE_INFORMATION, __PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION, objectstructures_54a0adde-cbf0-47c3-a1ab-aa426758c8b9.xml, PPUBLIC_OBJECT_TYPE_INFORMATION structure pointer [Installable File System Drivers], ntifs/PPUBLIC_OBJECT_TYPE_INFORMATION, PPUBLIC_OBJECT_TYPE_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : This structure is available starting with Microsoft Windows 2000.
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
req.typenames : PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# __PUBLIC_OBJECT_TYPE_INFORMATION structure
The PUBLIC_OBJECT_TYPE_INFORMATION structure holds the type name of the object.

## Syntax
````
typedef struct __PUBLIC_OBJECT_TYPE_INFORMATION {
  UNICODE_STRING TypeName;
  ULONG          Reserved[22];
} PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION;
````

## Members


`Reserved`

Reserved for system use.

`TypeName`

Specifies the type name of the object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |