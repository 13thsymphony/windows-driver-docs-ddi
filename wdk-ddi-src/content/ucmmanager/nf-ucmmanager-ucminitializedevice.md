---
UID: NF:ucmmanager.UcmInitializeDevice
title: UcmInitializeDevice function
author: windows-driver-content
description: Initializes the USB connector manager framework extension (UcmCx).
old-location: buses\ucminitializedevice.htm
old-project: usbref
ms.assetid: 9159A6ED-0D85-422D-936A-13D7EC907A7C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcmInitializeDevice, UcmInitializeDevice method [Buses], buses.ucminitializedevice, ucmmanager/UcmInitializeDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmInitializeDevice
product:
- Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# UcmInitializeDevice function
Initializes the USB connector manager framework extension (UcmCx).

## Syntax

```
NTSTATUS UcmInitializeDevice(
  WDFDEVICE           WdfDevice,
  PUCM_MANAGER_CONFIG Config
);
```

## Parameters

`WdfDevice`

A handle to a framework device object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

`Config`

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a> structure that is initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187933">UCM_MANAGER_CONFIG_INIT</a>.


## Return Value

<b>UcmInitializeDevice</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value.

## Remarks

This method initializes UcmCx and allocates resources required, registers for PnP events, and sets up I/O targets. The client driver must call this method in the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541693">EVT_WDF_DRIVER_DEVICE_ADD</a>  implementation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **Library** | UcmCxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187933">UCM_MANAGER_CONFIG_INIT</a>