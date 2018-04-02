---
UID: NS:wdm._PLUGPLAY_NOTIFICATION_HEADER
title: "_PLUGPLAY_NOTIFICATION_HEADER"
author: windows-driver-content
description: A PLUGPLAY_NOTIFICATION_HEADER structure is included at the beginning of each PnP notification structure, such as a DEVICE_INTERFACE_CHANGE_NOTIFICATION structure.
old-location: kernel\plugplay_notification_header.htm
old-project: kernel
ms.assetid: b2245810-8f3c-4955-b341-46df4a71707c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPLUGPLAY_NOTIFICATION_HEADER, PLUGPLAY_NOTIFICATION_HEADER, PLUGPLAY_NOTIFICATION_HEADER structure [Kernel-Mode Driver Architecture], PPLUGPLAY_NOTIFICATION_HEADER, PPLUGPLAY_NOTIFICATION_HEADER structure pointer [Kernel-Mode Driver Architecture], _PLUGPLAY_NOTIFICATION_HEADER, kernel.plugplay_notification_header, kstruct_c_3b18984d-35cf-4787-b887-a8916a89569b.xml, wdm/PLUGPLAY_NOTIFICATION_HEADER, wdm/PPLUGPLAY_NOTIFICATION_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PLUGPLAY_NOTIFICATION_HEADER
product: Windows
targetos: Windows
req.typenames: PLUGPLAY_NOTIFICATION_HEADER, *PPLUGPLAY_NOTIFICATION_HEADER
req.product: Windows 10 or later.
---

# _PLUGPLAY_NOTIFICATION_HEADER structure
A <b>PLUGPLAY_NOTIFICATION_HEADER</b> structure is included at the beginning of each PnP notification structure, such as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543134">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a> structure.

## Syntax
```
typedef struct _PLUGPLAY_NOTIFICATION_HEADER {
  USHORT Version;
  USHORT Size;
  GUID   Event;
} PLUGPLAY_NOTIFICATION_HEADER, *PPLUGPLAY_NOTIFICATION_HEADER;
```

## Members


`Version`

Specifies the version of the data structure, currently set to 1.

`Size`

Specifies the size of the structure, in bytes.

`Event`

Specifies a GUID identifying the event.

## Remarks
Drivers can cast a PnP notification structure to this type to access the <b>Event</b> field and identify the exact type of the structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543134">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547073">HWPROFILE_CHANGE_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564601">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>