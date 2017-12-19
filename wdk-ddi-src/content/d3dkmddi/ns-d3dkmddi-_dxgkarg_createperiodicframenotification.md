---
UID: NS.D3DKMDDI._DXGKARG_CREATEPERIODICFRAMENOTIFICATION
title: _DXGKARG_CREATEPERIODICFRAMENOTIFICATION
author: windows-driver-content
description: The arguments needed to create a periodic frame notification.
old-location: display\dxgkarg_createperiodicframenotification.htm
old-project: display
ms.assetid: 455C3FBD-2E0D-4CD7-B753-E53ED58A7F6F
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARG_CREATEPERIODICFRAMENOTIFICATION, DXGKARG_CREATEPERIODICFRAMENOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_CREATEPERIODICFRAMENOTIFICATION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGKARG_CREATEPERIODICFRAMENOTIFICATION structure



## -description
The arguments needed to create a periodic frame notification.



## -syntax

````
typedef struct _DXGKARG_CREATEPERIODICFRAMENOTIFICATION {
  HANDLE                         hAdapter;
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetID;
  UINT64                         Time;
  UINT                           NotificationID;
  HANDLE                         hNotification;
} DXGKARG_CREATEPERIODICFRAMENOTIFICATION;
````


## -struct-fields

### -field hAdapter

A handle to the adapter associated with VidPnSourceID.


### -field VidPnTargetID

The output that the compositor wishes to receive notifications for.


### -field Time

Represents an offset before the VSync. The Time value may not be longer than a VSync interval while in VSync mode. In units of 100ns.


### -field NotificationID

Represents an ID for the notification that will be used to track which interrupt has fired from the GPU.


### -field hNotification

A Handle to the notification object, later used to destroy the object.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>