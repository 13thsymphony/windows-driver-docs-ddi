---
UID : NS:d3dkmddi._DXGKARG_CREATEPERIODICFRAMENOTIFICATION
title : _DXGKARG_CREATEPERIODICFRAMENOTIFICATION
author : windows-driver-content
description : The arguments needed to create a periodic frame notification.
old-location : display\dxgkarg_createperiodicframenotification.htm
old-project : display
ms.assetid : 455C3FBD-2E0D-4CD7-B753-E53ED58A7F6F
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGKARG_CREATEPERIODICFRAMENOTIFICATION, DXGKARG_CREATEPERIODICFRAMENOTIFICATION, *INOUT_PDXGKARG_CREATEPERIODICFRAMENOTIFICATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGKARG_CREATEPERIODICFRAMENOTIFICATION
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DXGKARG_CREATEPERIODICFRAMENOTIFICATION
---

# _DXGKARG_CREATEPERIODICFRAMENOTIFICATION structure
The arguments needed to create a periodic frame notification.

## Syntax
````
typedef struct _DXGKARG_CREATEPERIODICFRAMENOTIFICATION {
  HANDLE                         hAdapter;
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetID;
  UINT64                         Time;
  UINT                           NotificationID;
  HANDLE                         hNotification;
} DXGKARG_CREATEPERIODICFRAMENOTIFICATION;
````

## Members

        
            `hAdapter`

            A handle to the adapter associated with VidPnSourceID.
        
            `hNotification`

            A Handle to the notification object, later used to destroy the object.
        
            `NotificationID`

            Represents an ID for the notification that will be used to track which interrupt has fired from the GPU.
        
            `Time`

            Represents an offset before the VSync. The Time value may not be longer than a VSync interval while in VSync mode. In units of 100ns.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h |