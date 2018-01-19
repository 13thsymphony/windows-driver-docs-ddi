---
UID : NF:ntddk.IoTransferActivityId
title : IoTransferActivityId function
author : windows-driver-content
description : The IoTransferActivityId routine logs an ETW transfer event using the I/O tracing provider on behalf of the caller. This allows a driver to associate two related activity IDs without requiring a specific provider to be enabled.
old-location : kernel\iotransferactivityid.htm
old-project : kernel
ms.assetid : BA6EBD60-B7D8-4EDE-A655-2F18F27E6299
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoTransferActivityId
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoTransferActivityId
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoTransferActivityId function
The IoTransferActivityId routine logs an ETW transfer event using the I/O tracing provider on behalf of the caller.  This allows a driver to associate two related activity IDs without requiring a specific provider to be enabled.

## Syntax

````
void IoTransferActivityId(
  _In_ LPCGUID ActivityId,
  _In_ LPCGUID RelatedActivityId
);
````

## Parameters

`ActivityId`

The source activity ID.

`RelatedActivityId`

The new activity ID to be transferred from the source activity ID.


## Return Value

None.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |