---
UID : NF:usbdlib.USBD_CreateHandle
title : USBD_CreateHandle function
author : windows-driver-content
description : The USBD_CreateHandle routine is called by a WDM USB client driver to obtain a USBD handle. The routine registers the client driver with the underlying USB driver stack.
old-location : buses\usbd_register.htm
old-project : usbref
ms.assetid : 97757CBA-8291-40A3-B247-D41E7FEB1D7C
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : USBD_CreateHandle
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : usbdlib.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBD_CreateHandle
req.alt-loc : Usbdex.lib,Usbdex.dll,Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Usbdex.lib; Ntstrsafe.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product : Windows 10 or later.
---


# USBD_CreateHandle function
The  <b>USBD_CreateHandle</b> routine is called by a WDM USB client driver to obtain a USBD handle. The routine registers the client driver with the underlying USB driver stack.

<b>Note for Windows Driver Framework (WDF) Drivers:  </b>If your client driver is a WDF-based driver, then you do not need the USBD handle. The client driver is registered in its call to the the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a> method.

## Syntax

````
NTSTATUS USBD_CreateHandle(
  _In_  PDEVICE_OBJECT DeviceObject,
  _In_  PDEVICE_OBJECT TargetDeviceObject,
  _In_  ULONG          USBDClientContractVersion,
  _In_  ULONG          PoolTag,
  _Out_ USBD_HANDLE    *USBDHandle
);
````

## Parameters

`DeviceObject`

Pointer to the device object for the client driver.

`TargetDeviceObject`

Pointer to the next lower device object in the device stack. The client driver receives a pointer to that device object in a previous call to <a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>.

`USBDClientContractVersion`

The contract version that the client driver supports. <i>USBDClientContractVersion</i> must be  USBD_CLIENT_CONTRACT_VERSION_602. For more information, see Remarks.

`PoolTag`

The pool tag used for memory allocations.

`USBDHandle`

Opaque handle that indicates that the client driver was registered with the USB driver stack. For more information, see Remarks.


## Return Value

The routine returns an NTSTATUS code. Possible  values include but are not limited to, these values in the following table.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine call succeeded.
<dl>
<dt><b>STATUS_INVALID_LEVEL</b></dt>
</dl>The caller is not running at the IRQL value PASSIVE_LEVEL.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The caller passed one of the following invalid parameter values:

## Remarks

Windows 8 includes a new USB driver stack to support USB 3.0 devices. The new USB driver stack provides several new capabilities, such as stream support, chained MDLs, and so on. 
Before your client driver can use any of those USB capabilities, you must register the client driver with the USB driver stack and obtain a USBD handle. The handle is required in order to call routines that use or configure the new capabilities. To obtain a USBD handle, call <b>USBD_CreateHandle</b>. 

The client driver must call <b>USBD_CreateHandle</b> regardless of whether the device is attached to a USB 3.0, 2.0, or 1.1 host controller. If the device is attached to a USB 3.0 host controller, Windows loads the USB 3.0 driver stack. Otherwise, USB 2.0 driver stack is loaded.   In either case, the client driver is <i>not</i> required to know the version supported by the underlying USB driver stack. <b>USBD_CreateHandle</b> assesses the driver stack version and allocates resources appropriately. 

The client driver must specify  USBD_CLIENT_CONTRACT_VERSION_602 in the <i>USBDClientContractVersion</i> parameter and follow the set of rules described in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406258">Best Practices: Using URBs</a>. 

The <b>USBD_CreateHandle</b> routine must be called by a Windows Driver Model (WDM) client driver before the driver  send any other requests, through URBs or IOCTLs, to the USB driver stack. Typically, the client driver obtains the USBD handle in its  AddDevice routine.   

A Windows Driver Frameworks (WDF) client driver is not required to call <b>USBD_CreateHandle</b> because the framework calls this routine on behalf of the client driver during the device initialization phase. Instead, the client driver can specify its client contract version in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_create_config.md">WDF_USB_DEVICE_CREATE_CONFIG</a> structure and pass it in the call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

If the  <b>USBD_CreateHandle</b> call succeeds,  a valid <i>USBD handle</i> is obtained in the <i>USBDHandle</i> parameter. The client driver must use the USBD handle in the client driver's future requests to the USB driver stack. 

If the <b>USBD_CreateHandle</b> call fails,  the client driver can fail the AddDevice routine.

After the client driver is finished using the USBD handle, the driver must close the handle  by calling the <a href="..\usbdlib\nf-usbdlib-usbd_closehandle.md">USBD_CloseHandle</a> routine.

The following example code shows how to register a client driver by calling <b>USBD_CreateHandle</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbdlib.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\usbdlib\nf-usbdlib-usbd_closehandle.md">USBD_CloseHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406258">Best Practices: Using URBs</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CreateHandle routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>