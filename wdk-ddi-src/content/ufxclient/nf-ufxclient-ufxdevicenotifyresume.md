---
UID: NF:ufxclient.UfxDeviceNotifyResume
title: UfxDeviceNotifyResume function
author: windows-driver-content
description: Notifies UFX about a USB bus resume event.
old-location: buses\ufxdevicenotifyresume.htm
old-project: usbref
ms.assetid: A89E9E65-937D-455F-A718-A6BC7611BB8F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ufxclient/UfxDeviceNotifyResume, UfxDeviceNotifyResume, UfxDeviceNotifyResume method [Buses], buses.ufxdevicenotifyresume
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ufxclient.h
apiname:
-	UfxDeviceNotifyResume
product: Windows
targetos: Windows
req.typenames: "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product: Windows 10 or later.
---


# UfxDeviceNotifyResume function
Notifies UFX about a USB bus resume event.

## Syntax

````
VOID UfxDeviceNotifyResume(
  [in] UFXDEVICE UfxDevice
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## Return Value

This method does not return a value.

## Remarks

The client driver calls <b>UfxDeviceNotifyResume</b> when it receives a bus resume event. The controller should return to the same state it was in at the time of the bus resume event.

The client driver typically calls <b>UfxDeviceNotifyResume</b> from its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function.  The following example shows how to handle a resume event.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    case DeviceEventWakeUp:
        if (ControllerContext-&gt;Suspended) {
            ControllerContext-&gt;Suspended = FALSE;
            UfxDeviceNotifyResume(ControllerContext-&gt;UfxDevice);
        }
        break;
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | ufxclient.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |