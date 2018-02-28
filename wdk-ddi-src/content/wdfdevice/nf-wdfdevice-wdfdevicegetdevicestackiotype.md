---
UID: NF:wdfdevice.WdfDeviceGetDeviceStackIoType
title: WdfDeviceGetDeviceStackIoType function
author: windows-driver-content
description: The WdfDeviceGetDeviceStackIoType method retrieves the buffer access methods that the framework is using for a device.
old-location: wdf\wdfdevicegetdevicestackiotype.htm
old-project: wdf
ms.assetid: E697F53C-2642-4E3F-AA8C-D0802B39D187
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDeviceGetDeviceStackIoType, WdfDeviceGetDeviceStackIoType method, wdf.wdfdevicegetdevicestackiotype, wdfdevice/WdfDeviceGetDeviceStackIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDeviceGetDeviceStackIoType
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetDeviceStackIoType function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceGetDeviceStackIoType</b> method retrieves the buffer access methods that the framework is using for a device.

## Syntax

````
void WdfDeviceGetDeviceStackIoType(
  _In_  WDFDEVICE          Device,
  _Out_ WDF_DEVICE_IO_TYPE *ReadWriteIoType,
  _Out_ WDF_DEVICE_IO_TYPE *IoControlIoType
);
````

## Parameters

`Device`

A handle to a framework device object.

`ReadWriteIoType`

A pointer to a driver-allocated location that receives a <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value. This value identifies the buffer access method that the framework is using for a device's read and write requests.

`IoControlIoType`

A pointer to a driver-allocated location that receives a <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value. This value that identifies the buffer access method that the framework is using for a device's I/O control requests.


## Return Value

This method does not return a value.

## Remarks

If your driver calls <b>WdfDeviceGetDeviceStackIoType</b> before the PnP manager has loaded all of the device's drivers, the values that <b>WdfDeviceGetDeviceStackIoType</b> retrieves might not be the values that it actually uses.

For more information about how the framework chooses a buffer access method, see <a href="https://msdn.microsoft.com/BDB78BCD-1964-431B-BE99-CABA6DF44D7A">Managing Buffer Access Methods in UMDF Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | WUDFx02000.lib |
| **DLL** | WUDFx02000.dll; TBD |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDeviceStackIoType method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>