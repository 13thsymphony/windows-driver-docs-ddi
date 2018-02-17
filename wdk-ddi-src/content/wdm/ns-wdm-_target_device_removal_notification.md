---
UID: NS:wdm._TARGET_DEVICE_REMOVAL_NOTIFICATION
title: "_TARGET_DEVICE_REMOVAL_NOTIFICATION"
author: windows-driver-content
description: The TARGET_DEVICE_REMOVAL_NOTIFICATION structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of EventCategoryTargetDeviceChange events.
old-location: kernel\target_device_removal_notification.htm
old-project: kernel
ms.assetid: a14656ca-131a-4722-aae7-041eddc8517a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_TARGET_DEVICE_REMOVAL_NOTIFICATION, PTARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION structure [Kernel-Mode Driver Architecture], wdm/PTARGET_DEVICE_REMOVAL_NOTIFICATION, *PTARGET_DEVICE_REMOVAL_NOTIFICATION, kernel.target_device_removal_notification, kstruct_d_9b46ee83-c40a-435c-a544-456672ebca33.xml, wdm/TARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION, PTARGET_DEVICE_REMOVAL_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	TARGET_DEVICE_REMOVAL_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: "*PTARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION"
req.product: Windows 10 or later.
---

# _TARGET_DEVICE_REMOVAL_NOTIFICATION structure
The <b>TARGET_DEVICE_REMOVAL_NOTIFICATION</b> structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryTargetDeviceChange</b> events.

## Syntax
````
typedef struct _TARGET_DEVICE_REMOVAL_NOTIFICATION {
  USHORT       Version;
  USHORT       Size;
  GUID         Event;
  PFILE_OBJECT FileObject;
} TARGET_DEVICE_REMOVAL_NOTIFICATION, *PTARGET_DEVICE_REMOVAL_NOTIFICATION;
````

## Members


`Event`

Specifies a GUID identifying the event: GUID_TARGET_DEVICE_QUERY_REMOVE, GUID_TARGET_DEVICE_REMOVE_COMPLETE, or GUID_TARGET_DEVICE_REMOVE_CANCELLED. These GUIDs are defined in Wdmguid.h.

`FileObject`

Pointer to a file object for the device.

`Size`

Specifies the size of the structure, in bytes, including the size of the standard first three members plus the event-specific data.

`Version`

Specifies the version of the data structure, currently set to 1.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>



<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TARGET_DEVICE_REMOVAL_NOTIFICATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>