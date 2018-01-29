---
UID : NF:wdfdevice.WdfDeviceGetDevicePowerState
title : WdfDeviceGetDevicePowerState function
author : windows-driver-content
description : The WdfDeviceGetDevicePowerState method returns the current state of the framework's power state machine, for a specified device.
old-location : wdf\wdfdevicegetdevicepowerstate.htm
old-project : wdf
ms.assetid : 7405e0c7-9263-4911-9b1e-52cffa559af3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfdevicegetdevicepowerstate, PFN_WDFDEVICEGETDEVICEPOWERSTATE, WdfDeviceGetDevicePowerState method, DFDeviceObjectGeneralRef_40013978-2c8d-4776-b218-5f0c743e57e9.xml, wdfdevice/WdfDeviceGetDevicePowerState, kmdf.wdfdevicegetdevicepowerstate, WdfDeviceGetDevicePowerState
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceGetDevicePowerState function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetDevicePowerState</b> method returns the current state of the framework's power state machine, for a specified device.

## Syntax

````
WDF_DEVICE_POWER_STATE WdfDeviceGetDevicePowerState(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object.


## Return Value

<b>WdfDeviceGetDevicePowerState</b> returns a <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_power_state.md">WDF_DEVICE_POWER_STATE</a>-typed enumerator that identifies the current state of the framework's power state machine for the specified device. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Most drivers do not need to be aware of the state of the framework's power state machine. For more information about the framework's state machines, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

The <b>WdfDeviceGetDevicePowerState</b> method returns a meaningful value only if it is called from within the following callback functions:
<ul>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled.md">EvtDeviceD0EntryPostInterruptsEnabled</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md">EvtDeviceSelfManagedIoSuspend</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md">WdfDeviceGetDevicePowerPolicyState</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevstatenormalize.md">WdfDevStateNormalize</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepnpstate.md">WdfDeviceGetDevicePnpState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDevicePowerState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>