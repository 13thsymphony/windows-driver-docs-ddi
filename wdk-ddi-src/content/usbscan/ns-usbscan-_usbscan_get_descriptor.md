---
UID : NS:usbscan._USBSCAN_GET_DESCRIPTOR
title : _USBSCAN_GET_DESCRIPTOR
author : windows-driver-content
description : The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_USB_DESCRIPTOR.
old-location : image\usbscan_get_descriptor.htm
old-project : image
ms.assetid : 250c0022-ceaa-40c6-8431-9ec53438fdb9
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : _USBSCAN_GET_DESCRIPTOR, *PUSBSCAN_GET_DESCRIPTOR, USBSCAN_GET_DESCRIPTOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbscan.h
req.include-header : Usbscan.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBSCAN_GET_DESCRIPTOR
req.alt-loc : usbscan.h
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
req.typenames : "*PUSBSCAN_GET_DESCRIPTOR, USBSCAN_GET_DESCRIPTOR"
req.product : Windows 10 or later.
---

# _USBSCAN_GET_DESCRIPTOR structure
The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_usb_descriptor.md">IOCTL_GET_USB_DESCRIPTOR</a>.

## Syntax
````
typedef struct _USBSCAN_GET_DESCRIPTOR {
  UCHAR  DescriptorType;
  UCHAR  Index;
  USHORT LanguageId;
} USBSCAN_GET_DESCRIPTOR, *PUSBSCAN_GET_DESCRIPTOR;
````

## Members

        
            `DescriptorType`

            Same as the <i>DescriptorType</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>.
        
            `Index`

            Same as the <i>Index</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.
        
            `LanguageId`

            Same as the <i>LanguageId</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbscan.h (include Usbscan.h) |