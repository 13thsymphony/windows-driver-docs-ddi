---
UID : NF:ufxclient.UfxDeviceNotifyHardwareReady
title : UfxDeviceNotifyHardwareReady function
author : windows-driver-content
description : Notifies UFX that the hardware is ready.
old-location : buses\ufxdevicenotifyhardwareready.htm
old-project : usbref
ms.assetid : B4BE0BDC-C1A3-4230-8F4B-78DE34F5554D
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UfxDeviceNotifyHardwareReady method [Buses], UfxDeviceNotifyHardwareReady, ufxclient/UfxDeviceNotifyHardwareReady, buses.ufxdevicenotifyhardwareready
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product : Windows 10 or later.
---


# UfxDeviceNotifyHardwareReady function
Notifies UFX that the hardware is ready.

## Syntax

````
VOID UfxDeviceNotifyHardwareReady(
  [in] UFXDEVICE UfxDevice
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## Return Value

This method does not return a value.

## Remarks

The client driver typically calls <b>UfxDeviceNotifyHardwareReady</b> from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function, as shown in the following example.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
OnEvtDeviceD0Entry (
  _In_ WDFDEVICE Device,
  _In_ WDF_POWER_DEVICE_STATE PreviousState
)
/*++

Routine Description:

    Called by the framework after entering D0 state.

Arguments:

    Device - WDFDEVICE framework handle to the bus FDO.

    PreviousState - The WDF_POWER_DEVICE_STATE from which the stack is
        making this transition.

Return Value:

    Returns STATUS_SUCCESS or an appropriate NTSTATUS code otherwise.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;

    TraceEntry();

    ControllerContext = DeviceGetControllerContext(Device);

    if (PreviousState &gt; WdfPowerDeviceD1) { 
        DevicePerformSoftReset(Device);

        WdfWaitLockAcquire(ControllerContext-&gt;InitializeDefaultEndpointLock, NULL);
        ControllerContext-&gt;InitializeDefaultEndpoint = TRUE;
        WdfWaitLockRelease(ControllerContext-&gt;InitializeDefaultEndpointLock);
    }

    if (PreviousState == WdfPowerDeviceD3Final) {
        //
        // Notify UFX that HW is now ready
        //
        UfxDeviceNotifyHardwareReady(ControllerContext-&gt;UfxDevice);
    }

    TraceExit();
    return STATUS_SUCCESS;
}</pre>
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