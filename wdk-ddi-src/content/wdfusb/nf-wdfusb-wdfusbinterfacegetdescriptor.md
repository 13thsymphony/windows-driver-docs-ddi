---
UID : NF:wdfusb.WdfUsbInterfaceGetDescriptor
title : WdfUsbInterfaceGetDescriptor function
author : windows-driver-content
description : The WdfUsbInterfaceGetDescriptor method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.
old-location : wdf\wdfusbinterfacegetdescriptor.htm
old-project : wdf
ms.assetid : 70156bfa-8271-42f6-9a22-0d0b77e63b66
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfUsbInterfaceGetDescriptor
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WdfUsbInterfaceGetDescriptor
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product : Windows 10 or later.
---


# WdfUsbInterfaceGetDescriptor function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetDescriptor</b> method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.

## Syntax

````
VOID WdfUsbInterfaceGetDescriptor(
  _In_  WDFUSBINTERFACE           UsbInterface,
  _In_  UCHAR                     SettingIndex,
  _Out_ PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor
);
````

## Parameters

`UsbInterface`

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>.

`SettingIndex`

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.

`InterfaceDescriptor`

A pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that the framework fills in.


## Return Value

None. 

If the <i>SettingIndex</i> value is invalid, the <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure can receive invalid data. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about the <b>WdfUsbInterfaceGetDescriptor</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example obtains the alternate setting index for a specified USB interface. Then, the example obtains the USB interface descriptor that represents the USB interface's current alternate setting.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<dl>
<dt>
<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>