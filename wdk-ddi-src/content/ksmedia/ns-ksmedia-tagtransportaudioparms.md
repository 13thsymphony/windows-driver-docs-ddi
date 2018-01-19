---
UID : NS:ksmedia.tagTRANSPORTAUDIOPARMS
title : tagTRANSPORTAUDIOPARMS
author : windows-driver-content
description : The TRANSPORTAUDIOPARMS structure is defined but not used.
old-location : stream\transportaudioparms.htm
old-project : stream
ms.assetid : 591ef01a-1a89-454a-ab58-a76813a9d4c2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagTRANSPORTAUDIOPARMS, *PTRANSPORTAUDIOPARMS, TRANSPORTAUDIOPARMS
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
req.alt-api : TRANSPORTAUDIOPARMS
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
req.typenames : "*PTRANSPORTAUDIOPARMS, TRANSPORTAUDIOPARMS"
---

# tagTRANSPORTAUDIOPARMS structure
The TRANSPORTAUDIOPARMS structure is defined but not used.

## Syntax
````
typedef struct tagTRANSPORTAUDIOPARMS {
  LONG EnableOutput;
  LONG EnableRecord;
  LONG EnableSelsync;
  LONG Input;
  LONG MonitorSource;
} TRANSPORTAUDIOPARMS, *PTRANSPORTAUDIOPARMS;
````

## Members

        
            `EnableOutput`

            Specifies the enable audio output. The default is ED_AUDIO_ALL.
        
            `EnableRecord`

            Specifies the enable audio record. The default is zero.
        
            `EnableSelsync`

            Specifies the selsync.
        
            `Input`

            Specifies the audio input to use. For example, specify zero to use the first (zeroth) audio input.
        
            `MonitorSource`

            Indicates the monitor source. The default is zero.

    ## Remarks
        Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |