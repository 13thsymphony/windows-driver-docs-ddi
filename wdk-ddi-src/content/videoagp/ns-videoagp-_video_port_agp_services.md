---
UID: NS.VIDEOAGP._VIDEO_PORT_AGP_SERVICES
title: _VIDEO_PORT_AGP_SERVICES
author: windows-driver-content
description: The VIDEO_PORT_AGP_SERVICES structure is obsolete and is supported only for backward compatibility with existing drivers. In its place, driver writers should use VIDEO_PORT_AGP_INTERFACE.
old-location: display\video_port_agp_services.htm
old-project: display
ms.assetid: 3e7d8f8e-a213-48ca-8a90-5d861271f6a2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES, PVIDEO_PORT_AGP_SERVICES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: videoagp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_PORT_AGP_SERVICES
req.alt-loc: videoagp.h
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
req.product: Windows 10 or later.
---

# _VIDEO_PORT_AGP_SERVICES structure



## -description
The VIDEO_PORT_AGP_SERVICES structure is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="display.video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a>.

The VIDEO_PORT_AGP_SERVICES structure describes the AGP service routines provided by the video port driver. PnP video miniport drivers that can use AGP should call <a href="display.videoportgetagpservices">VideoPortGetAgpServices</a> to initialize this structure. The video port driver initializes the entire structure; the miniport driver should never change any members.



## -syntax

````
typedef struct _VIDEO_PORT_AGP_SERVICES {
  PAGP_RESERVE_PHYSICAL AgpReservePhysical;
  PAGP_RELEASE_PHYSICAL AgpReleasePhysical;
  PAGP_COMMIT_PHYSICAL  AgpCommitPhysical;
  PAGP_FREE_PHYSICAL    AgpFreePhysical;
  PAGP_RESERVE_VIRTUAL  AgpReserveVirtual;
  PAGP_RELEASE_VIRTUAL  AgpReleaseVirtual;
  PAGP_COMMIT_VIRTUAL   AgpCommitVirtual;
  PAGP_FREE_VIRTUAL     AgpFreeVirtual;
  ULONGLONG             AllocationLimit;
} VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES;
````


## -struct-fields

### -field AgpReservePhysical


### -field AgpReleasePhysical


### -field AgpCommitPhysical


### -field AgpFreePhysical


### -field AgpReserveVirtual


### -field AgpReleaseVirtual


### -field AgpCommitVirtual


### -field AgpFreeVirtual


### -field AllocationLimit


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Videoagp.h</dt>
</dl>
</td>
</tr>
</table>