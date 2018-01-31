---
UID : NC:ks.PFNQUERYREFERENCESTRING
title : PFNQUERYREFERENCESTRING
author : windows-driver-content
description : This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool.
old-location : stream\kstrqueryreferencestring.htm
old-project : stream
ms.assetid : 08fd750f-19cc-4d78-a26b-9f790c5c3acf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.kstrqueryreferencestring, KStrQueryReferenceString routine [Streaming Media Devices], KStrQueryReferenceString, PFNQUERYREFERENCESTRING, PFNQUERYREFERENCESTRING, ks/KStrQueryReferenceString, ksfunc_ce750f42-efeb-4861-b451-ef0f8be40f9a.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
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
req.typenames : KEYWORDSELECTOR
---


# PFNQUERYREFERENCESTRING callback function
This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>.

## Syntax

```
PFNQUERYREFERENCESTRING Pfnqueryreferencestring;

NTSTATUS Pfnqueryreferencestring(
  PVOID Context,
  PWCHAR *String
)
{...}
```

## Parameters

`Context`

Pointer to a device extension of the device's PDO.

`*String`




## Return Value

None.

## Remarks

The driver can access this method through the <b>QueryReferenceString</b> member of the <a href="..\ks\ns-ks-bus_interface_reference.md">BUS_INTERFACE_REFERENCE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |