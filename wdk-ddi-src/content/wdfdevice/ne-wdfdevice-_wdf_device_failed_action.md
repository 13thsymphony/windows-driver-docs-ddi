---
UID: NE:wdfdevice._WDF_DEVICE_FAILED_ACTION
title: "_WDF_DEVICE_FAILED_ACTION"
author: windows-driver-content
description: The WDF_DEVICE_FAILED_ACTION enumeration identifies the action that the framework will take when a driver reports an unrecoverable software or hardware failure.
old-location: wdf\wdf_device_failed_action.htm
old-project: wdf
ms.assetid: 260fdda5-bc97-4522-96ca-1c29d41e8542
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdf_device_failed_action, _WDF_DEVICE_FAILED_ACTION, DFDeviceObjectGeneralRef_f23e41aa-e37c-45d0-b83b-0ee86eb24aba.xml, wdfdevice/WdfDeviceFailedNoRestart, kmdf.wdf_device_failed_action, wdfdevice/WdfDeviceFailedUndefined, WdfDeviceFailedUndefined, wdfdevice/WDF_DEVICE_FAILED_ACTION, WdfDeviceFailedAttemptRestart, WDF_DEVICE_FAILED_ACTION enumeration, wdfdevice/WdfDeviceFailedAttemptRestart, WDF_DEVICE_FAILED_ACTION, WdfDeviceFailedNoRestart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_DEVICE_FAILED_ACTION
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_FAILED_ACTION
req.product: Windows 10 or later.
---

# _WDF_DEVICE_FAILED_ACTION Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DEVICE_FAILED_ACTION enumeration identifies the action that the framework will take when a driver reports an unrecoverable software or hardware failure.

## Syntax
````
typedef enum _WDF_DEVICE_FAILED_ACTION { 
  WdfDeviceFailedUndefined       = 0,
  WdfDeviceFailedAttemptRestart  = 1,
  WdfDeviceFailedNoRestart       = 2
} WDF_DEVICE_FAILED_ACTION;
````

## Constants

<table>
            
                <tr>
                    <td>WdfDeviceFailedAttemptRestart</td>
                    <td>Supported in KMDF and starting in UMDF version 2.15.  If the device's drivers are not supporting other devices that are plugged into the computer, the I/O manager unloads the drivers. Next, the Plug and Play manager attempts to restart the device by requesting the bus driver to reenumerate its devices. If the bus driver supports reenumeration, your driver will be reloaded, if it was unloaded. If several consecutive restart attempts fail (because the restarted driver again reports an error), the framework stops trying to restart the device.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceFailedNoRestart</td>
                    <td>If the device's drivers are not supporting other devices on the system, the I/O manager unloads the drivers.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceFailedUndefined</td>
                    <td>For internal use only.</td>
                </tr>
</table>

    ## Remarks

        The WDF_DEVICE_FAILED_ACTION enumeration is used as an input argument to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetfailed.md">WdfDeviceSetFailed</a>.

Drivers typically specify <b>WdfDeviceFailedAttemptRestart</b> if they encounter an unrecoverable software error, because specifying this enumerator reloads the drivers. A driver might specify <b>WdfDeviceFailedNoRestart</b> if it encounters an unrecoverable hardware error that affects all of the driver's devices.

For information about specifying <b>WdfDeviceFailedAttemptRestart</b> in a UMDF driver, see the Remarks of <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetfailed.md">WdfDeviceSetFailed</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

    ## See Also

        <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetfailed.md">WdfDeviceSetFailed</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_FAILED_ACTION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>