---
UID: NS:video._VIDEO_PORT_AGP_INTERFACE_2
title: "_VIDEO_PORT_AGP_INTERFACE_2"
author: windows-driver-content
description: The VIDEO_PORT_AGP_INTERFACE_2 structure describes the AGP service routines provided by the video port driver.
old-location: display\video_port_agp_interface_2.htm
old-project: display
ms.assetid: 626cbf2d-2841-4b52-b17d-5377aa2f6264
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_PORT_AGP_INTERFACE_2, PVIDEO_PORT_AGP_INTERFACE_2, PVIDEO_PORT_AGP_INTERFACE_2 structure pointer [Display Devices], VIDEO_PORT_AGP_INTERFACE_2, VIDEO_PORT_AGP_INTERFACE_2 structure [Display Devices], Video_Structs_99a2957c-7304-4e59-9609-748a5d7b878b.xml, _VIDEO_PORT_AGP_INTERFACE_2, display.video_port_agp_interface_2, video/PVIDEO_PORT_AGP_INTERFACE_2, video/VIDEO_PORT_AGP_INTERFACE_2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_PORT_AGP_INTERFACE_2
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_INTERFACE_2, *PVIDEO_PORT_AGP_INTERFACE_2
req.product: Windows 10 or later.
---

# _VIDEO_PORT_AGP_INTERFACE_2 structure
The VIDEO_PORT_AGP_INTERFACE_2 structure describes the AGP service routines provided by the video port driver.

## Syntax
````
typedef struct _VIDEO_PORT_AGP_INTERFACE_2 {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PAGP_RESERVE_PHYSICAL  AgpReservePhysical;
  PAGP_RELEASE_PHYSICAL  AgpReleasePhysical;
  PAGP_COMMIT_PHYSICAL   AgpCommitPhysical;
  PAGP_FREE_PHYSICAL     AgpFreePhysical;
  PAGP_RESERVE_VIRTUAL   AgpReserveVirtual;
  PAGP_RELEASE_VIRTUAL   AgpReleaseVirtual;
  PAGP_COMMIT_VIRTUAL    AgpCommitVirtual;
  PAGP_FREE_VIRTUAL      AgpFreeVirtual;
  ULONGLONG              AgpAllocationLimit;
  PAGP_SET_RATE          AgpSetRate;
} VIDEO_PORT_AGP_INTERFACE_2, *PVIDEO_PORT_AGP_INTERFACE_2;
````

## Members


`Size`

Specifies the size in bytes of this structure.

`Version`

Specifies the version of the interface to be returned by the video port driver. The current interface version is defined in <i>video.h</i> and has the form VIDEO_PORT_AGP_INTERFACE_<i>N</i>.

`Context`

Pointer to a video port driver-defined context for the interface.

`InterfaceReference`

Pointer to the video port driver-implemented reference routine for this interface.

`InterfaceDereference`

Pointer to the video port driver-implemented dereference routine for this interface.

`AgpReservePhysical`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a> routine.

`AgpReleasePhysical`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_release_physical.md">AgpReleasePhysical</a> routine.

`AgpCommitPhysical`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a> routine.

`AgpFreePhysical`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a> routine.

`AgpReserveVirtual`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a> routine.

`AgpReleaseVirtual`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a> routine.

`AgpCommitVirtual`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a> routine.

`AgpFreeVirtual`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_free_virtual.md">AgpFreeVirtual</a> routine.

`AgpAllocationLimit`

Specifies the maximum total number of bytes of AGP memory that a miniport driver can commit.

`AgpSetRate`

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_set_rate.md">AgpSetRate</a> routine.

## Remarks
PnP video miniport drivers that can use AGP must fill in the <b>Size</b> and <b>Version</b> members, and then call the <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> function, which initializes the remaining members of this structure.

This structure is identical to the <a href="..\video\ns-video-_video_port_agp_interface.md">VIDEO_PORT_AGP_INTERFACE</a> structure, except for the <b>AgpSetRate</b> member, which that structure lacks. Video miniport drivers should first attempt to use VIDEO_PORT_AGP_INTERFACE_2 in a call to <b>VideoPortQueryServices</b>. If that call fails, due to the fact that the AGP filter driver does not support the newer version of the AGP interface, the video miniport driver can make a second call to <b>VideoPortQueryServices</b>, this time passing a VIDEO_PORT_AGP_INTERFACE structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>



<a href="..\video\ns-video-_video_port_agp_interface.md">VIDEO_PORT_AGP_INTERFACE</a>