---
UID: NS:usbfnattach._USBFN_INTERFACE_ATTACH
title: "_USBFN_INTERFACE_ATTACH"
author: windows-driver-content
description: Stores pointers to driver-implemented callback functions for handling attach and detach operations.
old-location: buses\usbfn_interface_attach.htm
old-project: usbref
ms.assetid: C7D7935C-0536-43E6-8924-1DC13B258007
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSBFN_INTERFACE_ATTACH, PUSBFN_INTERFACE_ATTACH, PUSBFN_INTERFACE_ATTACH structure pointer [Buses], USBFN_INTERFACE_ATTACH, USBFN_INTERFACE_ATTACH structure [Buses], _USBFN_INTERFACE_ATTACH, buses.usbfn_interface_attach, usbfnattach/PUSBFN_INTERFACE_ATTACH, usbfnattach/USBFN_INTERFACE_ATTACH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnattach.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnattach.h
api_name:
-	USBFN_INTERFACE_ATTACH
product:
- Windows
targetos: Windows
req.typenames: USBFN_INTERFACE_ATTACH, *PUSBFN_INTERFACE_ATTACH
req.product: Windows 10 or later.
---

# _USBFN_INTERFACE_ATTACH structure
Stores pointers to driver-implemented callback functions for handling attach and detach operations.

## Syntax
```
typedef struct _USBFN_INTERFACE_ATTACH {
  INTERFACE                         InterfaceHeader;
  PFN_USBFN_GET_ATTACH_ACTION       GetAttachAction;
  PFN_USBFN_GET_ATTACH_ACTION_ABORT GetAttachActionAbortOperation;
  PFN_USBFN_SET_DEVICE_STATE        SetDeviceState;
} USBFN_INTERFACE_ATTACH, *PUSBFN_INTERFACE_ATTACH;
```

## Members


`InterfaceHeader`

The interface version number.

`GetAttachAction`

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187995">USBFN_GET_ATTACH_ACTION</a> callback function.

`GetAttachActionAbortOperation`

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187996">USBFN_GET_ATTACH_ACTION_ABORT</a> callback function.

`SetDeviceState`

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188006">USBFN_SET_DEVICE_STATE</a> callback function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnattach.h |

## See Also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>