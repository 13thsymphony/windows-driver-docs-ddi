---
UID: NS:ucxusbdevice._USBDEVICE_ABORTIO
title: "_USBDEVICE_ABORTIO"
author: windows-driver-content
description: Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers.
old-location: buses\_usbdevice_abortio.htm
old-project: usbref
ms.assetid: 69720940-4D3E-43E6-B587-427ED2049FCC
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO structure pointer [Buses], USBDEVICE_ABORTIO, USBDEVICE_ABORTIO structure [Buses], _USBDEVICE_ABORTIO, buses._usbdevice_abortio, ucxusbdevice/P_USBDEVICE_ABORTIO, ucxusbdevice/_USBDEVICE_ABORTIO"
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
-	USBDEVICE_ABORTIO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_ABORTIO, *PUSBDEVICE_ABORTIO
req.product: Windows 10 or later.
---

# _USBDEVICE_ABORTIO structure
Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers.

## Syntax
````
typedef struct _USBDEVICE_ABORTIO {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_ABORTIO, *P_USBDEVICE_ABORTIO;
````

## Members


`Header`

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_startio.md">USBDEVICE_STARTIO</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_purgeio.md">USBDEVICE_PURGEIO</a>