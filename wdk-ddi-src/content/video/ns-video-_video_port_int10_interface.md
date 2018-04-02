---
UID: NS:video._VIDEO_PORT_INT10_INTERFACE
title: "_VIDEO_PORT_INT10_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.
old-location: display\video_port_int10_interface.htm
old-project: display
ms.assetid: 551b2255-c221-4a95-a812-dec34f09438b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVIDEO_PORT_INT10_INTERFACE, PVIDEO_PORT_INT10_INTERFACE, PVIDEO_PORT_INT10_INTERFACE structure pointer [Display Devices], VIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE structure [Display Devices], Video_Structs_b0f9d9fa-c989-4989-9f63-deb0ca211144.xml, _VIDEO_PORT_INT10_INTERFACE, display.video_port_int10_interface, video/PVIDEO_PORT_INT10_INTERFACE, video/VIDEO_PORT_INT10_INTERFACE"
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_PORT_INT10_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_INT10_INTERFACE, *PVIDEO_PORT_INT10_INTERFACE
req.product: Windows 10 or later.
---

# _VIDEO_PORT_INT10_INTERFACE structure
The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.

## Syntax
```
typedef struct _VIDEO_PORT_INT10_INTERFACE {
  IN USHORT                  Size;
  IN USHORT                  Version;
  OUT PVOID                  Context;
  OUT PINTERFACE_REFERENCE   InterfaceReference;
  OUT PINTERFACE_DEREFERENCE InterfaceDereference;
  OUT PINT10_ALLOCATE_BUFFER Int10AllocateBuffer;
  OUT PINT10_FREE_BUFFER     Int10FreeBuffer;
  OUT PINT10_READ_MEMORY     Int10ReadMemory;
  OUT PINT10_WRITE_MEMORY    Int10WriteMemory;
  OUT PINT10_CALL_BIOS       Int10CallBios;
} *PVIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE;
```

## Members


`Size`

Specifies the size in bytes of this structure.

`Version`

Specifies the version of the interface to be returned by the video port driver. The current interface version is defined in <i>video.h</i> and has the form VIDEO_PORT_INT10_INTERFACE_<i>N</i>.

`Context`

Pointer to a video port driver-defined context for the interface.

`InterfaceReference`

Pointer to the video port driver-implemented reference routine for this interface.

`InterfaceDereference`

Pointer to the video port driver-implemented dereference routine for this interface.

`Int10AllocateBuffer`

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/2e6c8000-13e3-46fb-81be-18428fec2b21">Int10AllocateBuffer</a> routine.

`Int10FreeBuffer`

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/feb7dd98-8c44-405e-8e98-ffd6246cf0ee">Int10FreeBuffer</a> routine.

`Int10ReadMemory`

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/94b72ad0-1ace-4fde-a4a9-1078103e3d9b">Int10ReadMemory</a> routine.

`Int10WriteMemory`

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/a1143ca4-9c39-4bd7-92e1-473bdb447eb5">Int10WriteMemory</a> routine.

`Int10CallBios`

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/994a73bc-81a1-4d73-959c-cc89b242c073">Int10CallBios</a> routine.

## Remarks
PnP video miniport drivers that intend to make BIOS calls should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>, which initializes the remaining members of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>