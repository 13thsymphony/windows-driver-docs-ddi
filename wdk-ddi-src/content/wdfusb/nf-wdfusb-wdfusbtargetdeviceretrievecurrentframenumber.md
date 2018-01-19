---
UID : NF:wdfusb.WdfUsbTargetDeviceRetrieveCurrentFrameNumber
title : WdfUsbTargetDeviceRetrieveCurrentFrameNumber function
author : windows-driver-content
description : The WdfUsbTargetDeviceRetrieveCurrentFrameNumber method retrieves the current USB frame number.
old-location : wdf\wdfusbtargetdeviceretrievecurrentframenumber.htm
old-project : wdf
ms.assetid : 7f73339f-adac-4569-92e7-1b166f93db92
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfUsbTargetDeviceRetrieveCurrentFrameNumber
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfUsbTargetDeviceRetrieveCurrentFrameNumber
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product : Windows 10 or later.
---


# WdfUsbTargetDeviceRetrieveCurrentFrameNumber function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> method retrieves the current USB frame number.

## Syntax

````
NTSTATUS WdfUsbTargetDeviceRetrieveCurrentFrameNumber(
  _In_  WDFUSBDEVICE UsbDevice,
  _Out_ PULONG       CurrentFrameNumber
);
````

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`CurrentFrameNumber`

A pointer to a location that receives the current 32-bit USB frame number.


## Return Value

<b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The frame number was unavailable, possibly because lower drivers do not provide frame numbers.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about the <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example calls <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b>. The example obtains a USB device object handle from driver-defined context space.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<dl>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceRetrieveCurrentFrameNumber method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>