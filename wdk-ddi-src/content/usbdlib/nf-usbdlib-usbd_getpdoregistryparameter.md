---
UID : NF:usbdlib.USBD_GetPdoRegistryParameter
title : USBD_GetPdoRegistryParameter function
author : windows-driver-content
description : The USBD_GetPdoRegistryParameter routine retrieves the value from the specified key in the USB device's hardware registry.
old-location : buses\usbd_getpdoregistryparameter.htm
old-project : usbref
ms.assetid : f61be32a-2537-4b7f-8f22-4149b00a15a4
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : USBD_GetPdoRegistryParameter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : usbdlib.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBD_GetPdoRegistryParameter
req.alt-loc : usbd.lib,usbd.dll
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
req.typenames : USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product : Windows 10 or later.
---


# USBD_GetPdoRegistryParameter function
The <b>USBD_GetPdoRegistryParameter</b> routine retrieves the value from the  specified key in the USB device's hardware registry.

## Syntax

````
NTSTATUS USBD_GetPdoRegistryParameter(
  _In_    PDEVICE_OBJECT PhysicalDeviceObject,
  _Inout_ PVOID          Parameter,
  _In_    ULONG          ParameterLength,
  _In_    PWSTR          KeyName,
  _In_    ULONG          KeyNameLength
);
````

## Parameters

`PhysicalDeviceObject`

Specifies the device object for the USB device.

`ParameterLength`

Size, in bytes, of the buffer that is pointed to by <i>Parameter</i>.

`KeyName`

Pointer to a string containing the name of the registry key.

`KeyNameLength`

Size, in bytes, of the buffer that is pointed to by <i>KeyName</i>.

`Parameter`

Pointer to a caller-allocated buffer that receives the registry value.


## Return Value

The <b>USBD_GetPdoRegistryParameter</b> returns STATUS_SUCCESS when the operation succeeds or an appropriate error status when the operation fails.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbdlib.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_GetPdoRegistryParameter routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>