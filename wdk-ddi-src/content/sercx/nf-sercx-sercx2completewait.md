---
UID: NF:sercx.SerCx2CompleteWait
title: SerCx2CompleteWait function
author: windows-driver-content
description: The SerCx2CompleteWait method notifies version 2 of the serial framework extension (SerCx2) that an event in the current wait mask has occurred.
old-location: serports\sercx2completewait.htm
old-project: serports
ms.assetid: 7A3DC90E-628C-4FFC-807D-8F23BDC97742
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2CompleteWait, 2/SerCx2CompleteWait, SerCx2CompleteWait method [Serial Ports], serports.sercx2completewait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2CompleteWait
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCx2CompleteWait function
The <b>SerCx2CompleteWait</b> method notifies version 2 of the serial framework extension (SerCx2) that an event in the current wait mask has occurred.

## Syntax

````
VOID SerCx2CompleteWait(
  [in] WDFDEVICE Device,
  [in] ULONG     Event
);
````

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.

`Event`

The type of event that is ending the current wait operation. This parameter is a wait mask value. Each event type corresponds to a particular bit in the wait mask. This bit is set to indicate that the corresponding event has occurred. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.


## Return Value

None.

## Remarks

When SerCx2 receives an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_set_wait_mask.md">EvtSerCx2SetWaitMask</a> callback function to notify the serial controller driver that the wait mask has changed.

When an event in the new wait mask occurs, the driver calls <b>SerCx2CompleteWait</b> to notify SerCx2 of the event. If a previously sent <a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a> request is pending in SerCx2 at the time of the <b>SerCx2CompleteWait</b> call, SerCx2 completes this request with an output wait mask that indicates which event occurred. Otherwise, SerCx2 stores the event in its internal event history in anticipation of a future <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CompleteWait method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>