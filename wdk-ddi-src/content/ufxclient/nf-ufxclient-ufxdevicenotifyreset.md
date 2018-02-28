---
UID: NF:ufxclient.UfxDeviceNotifyReset
title: UfxDeviceNotifyReset function
author: windows-driver-content
description: Notifies UFX about a USB bus reset event.
old-location: buses\ufxdevicenotifyreset.htm
old-project: usbref
ms.assetid: FD88E645-7CBB-4998-BEBA-5BBE2FF167FC
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDeviceNotifyReset, UfxDeviceNotifyReset method [Buses], buses.ufxdevicenotifyreset, ufxclient/UfxDeviceNotifyReset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceNotifyReset
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# UfxDeviceNotifyReset function
Notifies UFX about a USB bus reset event.

## Syntax

````
VOID UfxDeviceNotifyReset(
  [in] UFXDEVICE        UfxDevice,
  [in] USB_DEVICE_SPEED DeviceSpeed
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.

`DeviceSpeed`

Contains a value of type <a href="..\usbspec\ne-usbspec-_usb_device_speed.md">USB_DEVICE_SPEED</a> that indicates the speed of the device.


## Return Value

This method does not return a value.

## Remarks

The client driver calls <b>UfxDeviceNotifyReset</b> when it receives a bus reset event. All non-default endpoints should be disabled and the default endpoint should be reset.  The device moves to the default state.

The client driver typically calls <b>UfxDeviceNotifyReset</b> from its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function.  The following example shows how to handle a reset event.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
VOID
HandleUsbConnect (
    WDFDEVICE WdfDevice
    )
/*++

Routine Description:

    Handles a connect event from the controller.

Arguments:

    WDfDevice - WDFDEVICE object representing the controller.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;
    USB_DEVICE_SPEED DeviceSpeed;

    TraceEntry();

    ControllerContext = DeviceGetControllerContext(WdfDevice);

    //
    // Read the device speed.
    //

    //
    // #### TODO: Add code to read device speed from the controller ####
    //
    
    // Sample will assume SuperSpeed operation for illustration purposes
    DeviceSpeed = UsbSuperSpeed;
    
    //
    // #### TODO: Add any code needed to configure the controller after connect has occurred ####
    //


    ControllerContext-&gt;Speed = DeviceSpeed;
    TraceInformation("Connected Speed is %d!", DeviceSpeed);

    //
    // Notify UFX about reset, which will take care of updating 
    // Max Packet Size for EP0 by calling descriptor update.
    //
    UfxDeviceNotifyReset(ControllerContext-&gt;UfxDevice, DeviceSpeed);

    ControllerContext-&gt;Connect = TRUE;

    TraceExit();
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Header** | ufxclient.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |