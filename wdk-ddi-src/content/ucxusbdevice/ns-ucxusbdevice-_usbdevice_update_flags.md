---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FLAGS
title: "_USBDEVICE_UPDATE_FLAGS"
author: windows-driver-content
description: Contains request flags set by UCX that is passed in the USBDEVICE_UPDATE structure when UCX invokes the client driver's EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_flags.htm
old-project: usbref
ms.assetid: 36F009C8-046B-437A-83D6-AE8D5BF51AF3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: P_USBDEVICE_UPDATE_FLAGS, P_USBDEVICE_UPDATE_FLAGS structure pointer [Buses], USBDEVICE_UPDATE_FLAGS, USBDEVICE_UPDATE_FLAGS structure [Buses], _USBDEVICE_UPDATE_FLAGS, buses._usbdevice_update_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FLAGS
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
-	USBDEVICE_UPDATE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FLAGS
req.product: Windows 10 or later.
---

# _USBDEVICE_UPDATE_FLAGS structure
Contains request flags set by UCX that is  passed in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a> structure when UCX invokes the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187846">EVT_UCX_USBDEVICE_UPDATE</a> callback function.

## Syntax
```
typedef struct _USBDEVICE_UPDATE_FLAGS {
  ULONG  : 1  UpdateDeviceDescriptor;
  ULONG  : 1  UpdateBosDescriptor;
  ULONG  : 1  UpdateMaxExitLatency;
  ULONG  : 1  UpdateIsHub;
  ULONG  : 1  UpdateAllowIoOnInvalidPipeHandles;
  ULONG  : 1  Update20HardwareLpmParameters;
  ULONG  : 1  UpdateRootPortResumeTime;
  ULONG  : 26 Reserved;
} USBDEVICE_UPDATE_FLAGS;
```

## Members


`UpdateDeviceDescriptor`

If set, indicates a request to update the USB device descriptor.

`UpdateBosDescriptor`

If set, indicates a request to update the USB BOS descriptor.

`UpdateMaxExitLatency`

If set, indicates a request to update the maximum exit latency.

`UpdateIsHub`

If set, indicates a request to determine of the device is a hub.

`UpdateAllowIoOnInvalidPipeHandles`

If set, indicates the USB device or hub has been updated to allow I/O with invalid pipe handles.

`Update20HardwareLpmParameters`

If set, indicates a request to update the 2.0 LPM state.

`UpdateRootPortResumeTime`

If set, indicates a request to  update the root port resume time.

`Reserved`

Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188081">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188082">USBDEVICE_UPDATE_FAILURE_FLAGS</a>