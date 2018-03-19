---
UID: NS:wdm._HWPROFILE_CHANGE_NOTIFICATION
title: "_HWPROFILE_CHANGE_NOTIFICATION"
author: windows-driver-content
description: The HWPROFILE_CHANGE_NOTIFICATION structure describes an event related to a hardware profile configuration change.
old-location: kernel\hwprofile_change_notification.htm
old-project: kernel
ms.assetid: 3b6fe106-2440-4bc6-a3ae-9bb8b18f8094
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PHWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], PHWPROFILE_CHANGE_NOTIFICATION, PHWPROFILE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _HWPROFILE_CHANGE_NOTIFICATION, kernel.hwprofile_change_notification, kstruct_b_2e8d0c69-abe9-49a9-96f6-fba3b0020ff8.xml, wdm/HWPROFILE_CHANGE_NOTIFICATION, wdm/PHWPROFILE_CHANGE_NOTIFICATION"
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
-	Wdm.h
api_name:
-	HWPROFILE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: HWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION
req.product: Windows 10 or later.
---

# _HWPROFILE_CHANGE_NOTIFICATION structure
The <b>HWPROFILE_CHANGE_NOTIFICATION</b> structure describes an event related to a hardware profile configuration change. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryHardwareProfileChange</b> events.

## Syntax
````
typedef struct _HWPROFILE_CHANGE_NOTIFICATION {
  USHORT Version;
  USHORT Size;
  GUID   Event;
} HWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION;
````

## Members


`Version`

Specifies the version of the data structure, currently 1.

`Size`

Specifies the size of the structure, in bytes including the size of the standard first three members plus the event-specific data.

`Event`

Specifies a GUID identifying the event: GUID_HWPROFILE_QUERY_CHANGE, GUID_HWPROFILE_CHANGE_COMPLETE, or GUID_HWPROFILE_CHANGE_CANCELLED. The GUIDs are defined in Wdmguid.h.

## Remarks
There is no event-specific data for a hardware-profile-change event.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_plugplay_notification_header.md">PLUGPLAY_NOTIFICATION_HEADER</a>



<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>