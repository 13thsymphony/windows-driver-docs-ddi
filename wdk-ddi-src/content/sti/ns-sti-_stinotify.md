---
UID: NS:sti._STINOTIFY
title: "_STINOTIFY"
author: windows-driver-content
description: The STINOTIFY structure is used as a parameter to the IStillImage::LaunchApplicationForDevice, IStiDevice::GetLastNotificationData, and IStiUSD::GetNotificationData methods.
old-location: image\stinotify.htm
old-project: image
ms.assetid: 7dc42f9a-2e55-4ae5-a951-7d1d3b14564b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: stifnc_2cee63fa-a7a5-4a15-be83-e536a504bcb7.xml, *LPSTINOTIFY, image.stinotify, STINOTIFY, LPSTINOTIFY, sti/STINOTIFY, sti/LPSTINOTIFY, _STINOTIFY, LPSTINOTIFY structure pointer [Imaging Devices], STINOTIFY structure [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sti.h
apiname:
-	STINOTIFY
product: Windows
targetos: Windows
req.typenames: "*LPSTINOTIFY, STINOTIFY"
req.product: Windows 10 or later.
---

# _STINOTIFY structure
The STINOTIFY structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543796">IStillImage::LaunchApplicationForDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543751">IStiDevice::GetLastNotificationData</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543821">IStiUSD::GetNotificationData</a> methods.

## Syntax
````
typedef struct _STINOTIFY {
  DWORD dwSize;
  GUID  guidNotificationCode;
  BYTE  abNotificationData[MAX_NOTIFICATION_DATA];
} STINOTIFY, *LPSTINOTIFY;
````

## Members


`abNotificationData`

Byte array containing optional, vendor-defined information.

`dwSize`

Caller-supplied size, in bytes, of the STINOTIFY structure.

`guidNotificationCode`

GUID of the event. For more information, see <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sti.h (include Sti.h) |