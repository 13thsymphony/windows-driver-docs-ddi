---
UID : NS:ksmedia.tagTRANSPORTVIDEOPARMS
title : tagTRANSPORTVIDEOPARMS
author : windows-driver-content
description : The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future.
old-location : stream\transportvideoparms.htm
old-project : stream
ms.assetid : 14bc6133-78f1-4f25-8638-9348245180fa
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagTRANSPORTVIDEOPARMS, *PTRANSPORTVIDEOPARMS, TRANSPORTVIDEOPARMS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : TRANSPORTVIDEOPARMS
req.alt-loc : ksmedia.h
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
req.typenames : "*PTRANSPORTVIDEOPARMS, TRANSPORTVIDEOPARMS"
---

# tagTRANSPORTVIDEOPARMS structure
The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future.

## Syntax
````
typedef struct tagTRANSPORTVIDEOPARMS {
  LONG OutputMode;
  LONG Input;
} TRANSPORTVIDEOPARMS, *PTRANSPORTVIDEOPARMS;
````

## Members

        
            `Input`

            Specifies the video input to use. For example, specify zero to use the first (zeroth) video input.
        
            `OutputMode`

            Specifies the video output mode. For example ED_PLAYBACK.

    ## Remarks
        Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |