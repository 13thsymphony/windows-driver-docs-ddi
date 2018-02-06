---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE_FAILURE_FLAGS
title: "_USBDEVICE_ENABLE_FAILURE_FLAGS"
author: windows-driver-content
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_ENABLE callback function. Indicate errors, if any, that might have occurred while enabling the device.
old-location: buses\_usbdevice_enable_failure_flags.htm
old-project: usbref
ms.assetid: B239E637-2920-48A5-9F45-D3089140C8A2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_USBDEVICE_ENABLE_FAILURE_FLAGS, USBDEVICE_ENABLE_FAILURE_FLAGS, P_USBDEVICE_ENABLE_FAILURE_FLAGS structure pointer [Buses], P_USBDEVICE_ENABLE_FAILURE_FLAGS, buses._usbdevice_enable_failure_flags, ucxusbdevice/P_USBDEVICE_ENABLE_FAILURE_FLAGS, USBDEVICE_ENABLE_FAILURE_FLAGS structure [Buses], ucxusbdevice/_USBDEVICE_ENABLE_FAILURE_FLAGS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxusbdevice.h
apiname:
-	USBDEVICE_ENABLE_FAILURE_FLAGS
product: Windows
targetos: Windows
req.typenames: USBDEVICE_ENABLE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _USBDEVICE_ENABLE_FAILURE_FLAGS structure
The flags that are set by the client driver in the  <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback function. Indicate errors, if any, that might have occurred while enabling the device.

## Syntax
````
typedef struct _USBDEVICE_ENABLE_FAILURE_FLAGS {
  ULONG InsufficientHardwareResourcesForDefaultEndpoint  :1;
  ULONG InsufficientHardwareResourcesForDevice  :1;
  ULONG Reserved  :30;
} USBDEVICE_ENABLE_FAILURE_FLAGS, *P_USBDEVICE_ENABLE_FAILURE_FLAGS;
````

## Members


`InsufficientHardwareResourcesForDefaultEndpoint`

Insufficient  hardware resources for  transfers to the default endpoint.

`InsufficientHardwareResourcesForDevice`

Insufficient hardware resources to enable transfers.

`Reserved`

Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_enable.md">USBDEVICE_ENABLE</a>

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_ENABLE_FAILURE_FLAGS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>