---
UID : NS:ks.KSRELATIVEEVENT
title : KSRELATIVEEVENT
author : windows-driver-content
description : The KSPROPERTY_CONNECTION_STARTAT property is passed a KSRELATIVEEVENT structure.
old-location : stream\ksrelativeevent.htm
old-project : stream
ms.assetid : 4edb8b74-d5e5-49ee-85a7-9eb095f5a575
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSRELATIVEEVENT, KSRELATIVEEVENT
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
req.alt-api : KSRELATIVEEVENT
req.alt-loc : ks.h
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
req.typenames : KSRELATIVEEVENT
---

# KSRELATIVEEVENT structure
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff565109">KSPROPERTY_CONNECTION_STARTAT</a> property is passed a KSRELATIVEEVENT structure.

## Syntax
````
typedef struct {
  ULONG       Size;
  ULONG       Flags;
  union {
    HANDLE ObjectHandle;
    PVOID  ObjectPointer;
  };
  PVOID       Reserved;
  KSEVENT     Event;
  KSEVENTDATA EventData;
} KSRELATIVEEVENT;
````

## Members

        
            `Event`

            A <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> structure that contains the event to be used.
        
            `EventData`

            A <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that specifies the header for the event-specific data. The header itself is not actually used except as a starting point to access the event-specific data, and must be initialized to zero.
        
            `Flags`

            Specifies what type of object is specified in the <b>ObjectHandle</b> and <b>ObjectPointer</b> union.
        
            `Reserved`

            Reserved and set to zero.
        
            `Size`

            Specifies the inclusive size of the structure, including any event specific data appended to the <b>EventData</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |