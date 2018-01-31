---
UID : NF:usbdlib.USBD_ValidateConfigurationDescriptor
title : USBD_ValidateConfigurationDescriptor function
author : windows-driver-content
description : The USBD_ValidateConfigurationDescriptor routine validates all descriptors returned by a device in its response to a configuration descriptor request.
old-location : buses\usbd_validateconfigurationdescriptor.htm
old-project : usbref
ms.assetid : 2fbe08ca-a9eb-4e3b-aa28-1ff34ad22a46
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : USBD_ValidateConfigurationDescriptor routine [Buses], usbdlib/USBD_ValidateConfigurationDescriptor, USBD_ValidateConfigurationDescriptor, buses.usbd_validateconfigurationdescriptor
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : usbdlib.h
req.include-header : Usbdlib.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Usbd.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product : Windows 10 or later.
---


# USBD_ValidateConfigurationDescriptor function
The <b>USBD_ValidateConfigurationDescriptor</b> routine validates all descriptors returned by a device in its response to a configuration descriptor request.

## Syntax

````
USBD_STATUS USBD_ValidateConfigurationDescriptor(
  _In_     PUSB_CONFIGURATION_DESCRIPTOR ConfigDesc,
  _In_     ULONG                         BufferLength,
  _In_     USHORT                        Level,
  _Out_    PUCHAR                        *Offset,
  _In_opt_ ULONG                         Tag
);
````

## Parameters

`ConfigDesc`

Pointer to a configuration descriptor that includes all interface, endpoint, vendor, and class-specific descriptors retrieved from a USB device.

`BufferLength`

Size, in bytes, of the configuration descriptor being validated.

`Level`

Level of validation to be performed.  The following are valid values:
<ul>
<li>1-Basic validation of the configuration descriptor header.</li>
<li>2-Full validation of the configuration descriptor including checking for invalid endpoint addresses, interface numbers, descriptor structures, interface alternate settings, number of interfaces and <b>bLength</b> fields of all descriptors.               
</li>
<li>3-In addition to the validation for levels 1 and 2, level 3 validates plus validates the number of endpoints in each interface, enforces the USB specification's descriptor <b>bLength</b> sizes, and verifies that all interface numbers are in sequential order.</li>
</ul>

`Offset`

Offset within configuration descriptor where validation failed.  Only valid when a status other than USBD_STATUS_SUCCESS is returned.

`Tag`

Pool tag used by <b>USBD_ValidateConfigurationDescriptor</b> when allocating memory.


## Return Value

USBD_STATUS_SUCCESS, or appropriate USBD error code if validation failed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbdlib.h (include Usbdlib.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ValidateConfigurationDescriptor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>