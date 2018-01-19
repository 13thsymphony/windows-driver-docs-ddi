---
UID : NS:ks._KSEVENT_ENTRY
title : _KSEVENT_ENTRY
author : windows-driver-content
description : The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered.
old-location : stream\ksevent_entry.htm
old-project : stream
ms.assetid : 2d246109-839d-46fd-9898-9e059b803790
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _KSEVENT_ENTRY, *PKSEVENT_ENTRY, KSEVENT_ENTRY
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
req.alt-api : KSEVENT_ENTRY
req.alt-loc : Ks.h
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
req.typenames : "*PKSEVENT_ENTRY, KSEVENT_ENTRY"
---

# _KSEVENT_ENTRY structure
The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered.

## Syntax
````
typedef struct _KSEVENT_ENTRY {
  LIST_ENTRY        ListEntry;
  PVOID             Object;
  union {
    PKSDPC_ITEM    DpcItem;
    PKSBUFFER_ITEM BufferItem;
  };
  PKSEVENTDATA      EventData;
  const KSEVENT_SET NotificationType;
  const             *EventSet;
  KSEVENT_ITEM      *EventItem;
  PFILE_OBJECT      FileObject;
  ULONG             SemaphoreAdjustment;
  ULONG             Reserved;
  ULONG             Flags;
} KSEVENT_ENTRY;
````

## Members


    ## Remarks
        Drivers that do not provide an <a href="..\ks\nc-ks-pfnksremoveevent.md">AVStrMiniRemoveEvent</a> handler should treat this as an opaque data structure.

For more information, see <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |