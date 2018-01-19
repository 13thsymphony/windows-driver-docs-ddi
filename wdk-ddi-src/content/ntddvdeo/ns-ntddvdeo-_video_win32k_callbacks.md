---
UID : NS:ntddvdeo._VIDEO_WIN32K_CALLBACKS
title : _VIDEO_WIN32K_CALLBACKS
author : windows-driver-content
description : The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.
old-location : display\video_win32k_callbacks.htm
old-project : display
ms.assetid : dec6c610-811c-40cb-a099-1a35b91d2ee8
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS, VIDEO_WIN32K_CALLBACKS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddvdeo.h
req.include-header : Ntddvdeo.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VIDEO_WIN32K_CALLBACKS
req.alt-loc : ntddvdeo.h
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
req.typenames : "*PVIDEO_WIN32K_CALLBACKS, VIDEO_WIN32K_CALLBACKS"
---

# _VIDEO_WIN32K_CALLBACKS structure
The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.

## Syntax
````
typedef struct _VIDEO_WIN32K_CALLBACKS {
  PVOID                 PhysDisp;
  PVIDEO_WIN32K_CALLOUT Callout;
  ULONG                 bACPI;
  HANDLE                pPhysDeviceObject;
  ULONG                 DualviewFlags;
} VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS;
````

## Members

        
            `bACPI`

            Reserved for system use.
        
            `Callout`

            Reserved for system use.
        
            `DualviewFlags`

            Reserved for system use.
        
            `PhysDisp`

            Reserved for system use.
        
            `pPhysDeviceObject`

            Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |