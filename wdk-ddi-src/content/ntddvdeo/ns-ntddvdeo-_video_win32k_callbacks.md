---
UID: NS:ntddvdeo._VIDEO_WIN32K_CALLBACKS
title: "_VIDEO_WIN32K_CALLBACKS"
author: windows-driver-content
description: The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.
old-location: display\video_win32k_callbacks.htm
old-project: display
ms.assetid: dec6c610-811c-40cb-a099-1a35b91d2ee8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVIDEO_WIN32K_CALLBACKS, PVIDEO_WIN32K_CALLBACKS, PVIDEO_WIN32K_CALLBACKS structure pointer [Display Devices], VIDEO_WIN32K_CALLBACKS, VIDEO_WIN32K_CALLBACKS structure [Display Devices], Video_Structs_3c169102-2431-4217-b9e2-80ef23ee8096.xml, _VIDEO_WIN32K_CALLBACKS, display.video_win32k_callbacks, ntddvdeo/PVIDEO_WIN32K_CALLBACKS, ntddvdeo/VIDEO_WIN32K_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddvdeo.h
api_name:
-	VIDEO_WIN32K_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS
---

# _VIDEO_WIN32K_CALLBACKS structure
The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.

## Syntax
```
typedef struct _VIDEO_WIN32K_CALLBACKS {
  IN PVOID                 PhysDisp;
  IN PVIDEO_WIN32K_CALLOUT Callout;
  OUT ULONG                bACPI;
  OUT HANDLE               pPhysDeviceObject;
  OUT ULONG                DualviewFlags;
} VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS;
```

## Members


`PhysDisp`

Reserved for system use.

`Callout`

Reserved for system use.

`bACPI`

Reserved for system use.

`pPhysDeviceObject`

Reserved for system use.

`DualviewFlags`

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |