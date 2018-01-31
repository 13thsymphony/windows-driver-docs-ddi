---
UID : NF:ntddk.IoGetSiloParameters
title : IoGetSiloParameters function
author : windows-driver-content
description : This routine indicates if a file is within a Container context.
old-location : ifsk\iogetsiloparameters.htm
old-project : ifsk
ms.assetid : C8F42E83-2122-4871-972B-9FD06379C271
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IoGetSiloParameters function [Installable File System Drivers], PIO_FOEXT_SILO_PARAMETERS, ntddk/IoGetSiloParameters, ifsk.iogetsiloparameters, IoGetSiloParameters
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoGetSiloParameters function
This routine indicates if a file is within a Container context.

## Syntax

````
PIO_FOEXT_SILO_PARAMETERS IoGetSiloParameters(
  _In_ PFILE_OBJECT FileObject
);
````

## Parameters

`FileObject`

The file in question.


## Return Value

If <b>null</b>, the file is not in a container context. Otherwise, a non-null value of type <a href="..\ntddk\ns-ntddk-_io_foext_silo_parameters.md">IO_FOEXT_SILO_PARAMETERS</a> indicates that the file is within a Container context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |