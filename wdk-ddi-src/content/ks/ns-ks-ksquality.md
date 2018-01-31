---
UID : NS:ks.KSQUALITY
title : KSQUALITY
author : windows-driver-content
description : The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.
old-location : stream\ksquality.htm
old-project : stream
ms.assetid : 36caaea9-2354-4ed8-9649-5eb102def8d5
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKSQUALITY, ks/KSQUALITY, *PKSQUALITY, KSQUALITY structure [Streaming Media Devices], KSQUALITY, ks/PKSQUALITY, stream.ksquality, PKSQUALITY structure pointer [Streaming Media Devices], ks-struct_a2b63e1c-e5b4-437d-a5ba-0746f8388eef.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
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
req.typenames : "*PKSQUALITY, KSQUALITY"
---

# KSQUALITY structure
The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.

## Syntax
````
typedef struct {
  PVOID    Context;
  ULONG    Proportion;
  LONGLONG DeltaTime;
} KSQUALITY, *PKSQUALITY;
````

## Members


`Context`

Specifies a context parameter that was originally passed to the connection.

`DeltaTime`

Indicates the delta in native units (as indicated by the Interface) from optimal time at which the frames are being delivered, where a positive number means too late, and a negative number means too early. Zero indicates a correct delta.

`Proportion`

Indicates the percentage of frames currently being received that are actually being used. This is expressed in units of one-tenth of a percent, where 1000 is optimal.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |