---
UID: NS:ucxusbdevice._USBDEVICE_STARTIO
title: "_USBDEVICE_STARTIO"
author: windows-driver-content
description: Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer.
old-location: buses\_usbdevice_startio.htm
old-project: usbref
ms.assetid: 6FE2962A-90A3-44C6-9A2E-CCEBCE8C1417
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSBDEVICE_STARTIO, P_USBDEVICE_STARTIO, P_USBDEVICE_STARTIO structure pointer [Buses], USBDEVICE_STARTIO, USBDEVICE_STARTIO structure [Buses], _USBDEVICE_STARTIO, buses._usbdevice_startio, ucxusbdevice/P_USBDEVICE_STARTIO, ucxusbdevice/_USBDEVICE_STARTIO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	ucxusbdevice.h
api_name:
-	USBDEVICE_STARTIO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_STARTIO, *PUSBDEVICE_STARTIO
req.product: Windows 10 or later.
---

# _USBDEVICE_STARTIO structure
Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer.

## Syntax
```
typedef struct _USBDEVICE_STARTIO {
  USBDEVICE_MGMT_HEADER Header;
} USBDEVICE_STARTIO, *PUSBDEVICE_STARTIO;
```

## Members


`Header`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188069">USBDEVICE_ABORTIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188076">USBDEVICE_PURGEIO</a>