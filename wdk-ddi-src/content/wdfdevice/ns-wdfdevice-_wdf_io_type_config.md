---
UID : NS:wdfdevice._WDF_IO_TYPE_CONFIG
title : "_WDF_IO_TYPE_CONFIG"
author : windows-driver-content
description : The WDF_IO_TYPE_CONFIG structure specifies the driver's preferred buffer access method for read and write requests, and for device I/O control requests.
old-location : wdf\wdf_io_type_config.htm
old-project : wdf
ms.assetid : EB3CEC0E-5635-410D-B8D2-031FDB0557C1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WDF_IO_TYPE_CONFIG structure, WDF_IO_TYPE_CONFIG, _WDF_IO_TYPE_CONFIG, wdfdevice/PWDF_IO_TYPE_CONFIG, wdfdevice/WDF_IO_TYPE_CONFIG, *PWDF_IO_TYPE_CONFIG, PWDF_IO_TYPE_CONFIG structure pointer, PWDF_IO_TYPE_CONFIG, wdf.wdf_io_type_config
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_IO_TYPE_CONFIG, WDF_IO_TYPE_CONFIG"
req.product : Windows 10 or later.
---

# _WDF_IO_TYPE_CONFIG structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TYPE_CONFIG</b> structure specifies the driver's preferred buffer access method for read and write requests, and for device I/O control requests.

## Syntax
````
typedef struct _WDF_IO_TYPE_CONFIG {
  ULONG              Size;
  WDF_DEVICE_IO_TYPE ReadWriteIoType;
  WDF_DEVICE_IO_TYPE DeviceControlIoType;
  ULONG              DirectTransferThreshold;
} WDF_IO_TYPE_CONFIG, *PWDF_IO_TYPE_CONFIG;
````

## Members


`DeviceControlIoType`

This member does not apply to KMDF.

<b>UMDF </b>A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that you prefer the driver use for the data 
    buffers of IOCTL requests. Valid values include <b>WdfDeviceIoBuffered</b>           and <b>WdfDeviceIoDirect</b>.

`DirectTransferThreshold`

This member does not apply to KMDF.

<b>UMDF </b>An optional value that specifies the smallest buffer size, in bytes, for which 
    the framework will use direct I/O for a device. For example, set 
    <b>DirectTransferThreshold</b> to 12288 to indicate that the framework should use buffered I/O for all buffers that are smaller than 12 kilobytes, and direct I/O for buffers that are equal to or larger than 12 kilobytes. Typically, you 
    do not need to provide this value because the framework uses settings  that provide
    the best performance.

`ReadWriteIoType`

<b>KMDF </b>A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that the driver will use to access data buffers 
    that it receives for read and write requests.


<b>UMDF </b>A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that you prefer the driver use to access data buffers of read and write requests. Valid values include <b>WdfDeviceIoBuffered</b>           and <b>WdfDeviceIoDirect</b>.

`Size`

Size of this structure in bytes.

## Remarks
The <b>WDF_IO_TYPE_CONFIG</b> structure is used as input to the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a> method.

To initialize a <b>WDF_IO_TYPE_CONFIG</b> structure, your driver should call <a href="..\wdfdevice\nf-wdfdevice-wdf_io_type_config_init.md">WDF_IO_TYPE_CONFIG_INIT</a>.

If you are writing a driver using UMDF version 2.0 or later, see <a href="https://msdn.microsoft.com/BDB78BCD-1964-431B-BE99-CABA6DF44D7A">Managing Buffer Access Methods in UMDF Drivers</a> for more information about specifying preferred buffer access methods.


If you are writing a driver using UMDF version 1.<i>x</i>, your driver calls <a href="https://msdn.microsoft.com/7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0"> IWDFDeviceInitialize2::SetIoTypePreference</a> to specify preferred buffer access methods.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>

<a href="..\wdfdevice\nf-wdfdevice-wdf_io_type_config_init.md">WDF_IO_TYPE_CONFIG_INIT</a>

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TYPE_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>