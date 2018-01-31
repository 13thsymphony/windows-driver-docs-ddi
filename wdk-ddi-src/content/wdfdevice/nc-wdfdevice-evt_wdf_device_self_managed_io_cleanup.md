---
UID : NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
title : EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP
author : windows-driver-content
description : A driver's EvtDeviceSelfManagedIoCleanup event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.
old-location : wdf\evtdeviceselfmanagediocleanup.htm
old-project : wdf
ms.assetid : 639ff3fd-ce38-417e-8fc4-a03ad259a5c8
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtdeviceselfmanagediocleanup, EvtDeviceSelfManagedIoCleanup callback function, EvtDeviceSelfManagedIoCleanup, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP, EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP, wdfdevice/EvtDeviceSelfManagedIoCleanup, DFDeviceObjectGeneralRef_73e3f47e-1f3d-4dee-9fb2-62acbb5aaea2.xml, kmdf.evtdeviceselfmanagediocleanup
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DEVICE_SHUTDOWN_FLAGS
req.product : Windows 10 or later.
---


# EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoCleanup</i> event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed.

## Syntax

```
EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP EvtWdfDeviceSelfManagedIoCleanup;

void EvtWdfDeviceSelfManagedIoCleanup(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

None

## Remarks

To register an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoCleanup</i> callback function, the framework calls it after the specified device has been removed from the system. For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

The framework calls the driver's <i>EvtDeviceSelfManagedIoCleanup</i> callback function after it has called the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md">EvtDeviceSelfManagedIoSuspend</a> callback function. The <i>EvtDeviceSelfManagedIoCleanup</i> callback function must release any system resources that the driver allocated and associated with the device's self-managed I/O operations. 

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md">EvtDeviceSelfManagedIoSuspend</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md">EvtDeviceSelfManagedIoFlush</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>