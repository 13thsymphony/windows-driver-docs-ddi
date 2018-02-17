---
UID: NF:ucxclass.UcxInitializeDeviceInit
title: UcxInitializeDeviceInit function
author: windows-driver-content
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\_ucxinitializedeviceinit.htm
old-project: usbref
ms.assetid: A92A3E2E-1C73-40BD-808A-CBC14404F3E9
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses._ucxinitializedeviceinit, UcxInitializeDeviceInit method [Buses], UcxInitializeDeviceInit, ucxclass/UcxInitializeDeviceInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxclass.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxclass.h
apiname:
-	UcxInitializeDeviceInit
product: Windows
targetos: Windows
req.typenames: "*PUCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT"
req.product: Windows 10 or later.
---


# UcxInitializeDeviceInit function
Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## Syntax

````
NTSTATUS UcxInitializeDeviceInit(
  [in, out] PWDFDEVICE_INIT DeviceInit
);
````

## Parameters

`DeviceInit`

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## Return Value

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

The client driver for the host controller calls this method in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> implementation before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Header** | ucxclass.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxInitializeDeviceInit method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>