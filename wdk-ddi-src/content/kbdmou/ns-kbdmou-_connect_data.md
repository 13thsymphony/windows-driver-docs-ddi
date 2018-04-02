---
UID: NS:kbdmou._CONNECT_DATA
title: "_CONNECT_DATA"
author: windows-driver-content
description: CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.
old-location: hid\connect_data__kbdclass_.htm
old-project: hid
ms.assetid: 8fdb5b1d-bbdb-4774-875a-7cdd047286f5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PCONNECT_DATA, CONNECT_DATA, CONNECT_DATA structure [Human Input Devices], PCONNECT_DATA, PCONNECT_DATA structure pointer [Human Input Devices], _CONNECT_DATA, hid.connect_data__kbdclass_, kbdmou/CONNECT_DATA, kbdmou/PCONNECT_DATA, kref_e50b6d57-99fa-41bd-979c-de2d83922af6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: kbdmou.h
req.include-header: Kbdmou.h
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
-	kbdmou.h
api_name:
-	CONNECT_DATA
product:
- Windows
targetos: Windows
req.typenames: CONNECT_DATA, *PCONNECT_DATA
---

# _CONNECT_DATA structure
CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.

## Syntax
```
typedef struct _CONNECT_DATA {
  IN PDEVICE_OBJECT ClassDeviceObject;
  IN PVOID          ClassService;
} CONNECT_DATA, *PCONNECT_DATA;
```

## Members


`ClassDeviceObject`

Pointer to an upper-level class <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">filter device object</a> (filter DO).

`ClassService`

Specifies the class service routine. See  <a href="https://msdn.microsoft.com/library/windows/hardware/ff542274">PSERVICE_CALLBACK_ROUTINE</a>.

## Remarks
The keyboard class driver uses this structure with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541273">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request; the mouse class driver uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff541294">IOCTL_INTERNAL_MOUSE_CONNECT</a> .

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | kbdmou.h (include Kbdmou.h) |