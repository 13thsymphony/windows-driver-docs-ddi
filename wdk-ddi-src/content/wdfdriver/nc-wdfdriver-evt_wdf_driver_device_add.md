---
UID : NC:wdfdriver.EVT_WDF_DRIVER_DEVICE_ADD
title : EVT_WDF_DRIVER_DEVICE_ADD
author : windows-driver-content
description : A driver's EvtDriverDeviceAdd event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location : wdf\evtdriverdeviceadd.htm
old-project : wdf
ms.assetid : b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtdriverdeviceadd, EvtDriverDeviceAdd callback function, EvtDriverDeviceAdd, EVT_WDF_DRIVER_DEVICE_ADD, EVT_WDF_DRIVER_DEVICE_ADD, wdfdriver/EvtDriverDeviceAdd, DFDriverObjectRef_9b5ff898-9b1b-4eb6-87f7-42bee5deab18.xml, kmdf.evtdriverdeviceadd
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfdriver.h
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
req.typenames : "*PWDF_DPC_CONFIG, WDF_DPC_CONFIG"
req.product : Windows 10 or later.
---


# EVT_WDF_DRIVER_DEVICE_ADD function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDriverDeviceAdd</i> event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## Syntax

```
EVT_WDF_DRIVER_DEVICE_ADD EvtWdfDriverDeviceAdd;

NTSTATUS EvtWdfDriverDeviceAdd(
  WDFDRIVER Driver,
  PWDFDEVICE_INIT DeviceInit
)
{...}
```

## Parameters

`Driver`

A handle to a framework driver object that represents the driver.

`DeviceInit`

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## Return Value

The<i>EvtDriverDeviceAdd</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this callback function must return one of the error status values that are defined in <i>Ntstatus.h</i>. For more information, see the following Remarks section.

## Remarks

Each framework-based driver that supports PnP devices must provide the <i>EvtDriverDeviceAdd</i> callback function. The driver must place the callback function's address in its <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure before calling <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>.

The framework calls your driver's <i>EvtDriverDeviceAdd</i> callback function after a bus driver detects a device that has a hardware identifier (ID) that matches a hardware ID that your driver supports. You specify the hardware IDs that your driver supports by providing an INF file, which the operating system uses to install drivers the first time that one of your devices is connected to the computer. For more information about how the system uses INF files and hardware IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

A driver's <i>EvtDriverDeviceAdd</i> callback function typically performs at least some of the following initialization operations:
<ul>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Create a framework device object</a> to represent the device.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Create I/O queues</a> so the driver can receive I/O requests.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces">Create device interfaces</a> that applications use to communicate with the device.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Create driver-defined interfaces</a> that other drivers can use.

</li>
<li>
Initialize <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a> support.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-an-interrupt-object">Create interrupt objects</a>, if the driver handles device interrupts.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enable direct memory access (DMA) transactions</a>, if the driver handles DMA operations.

</li>
</ul>Some drivers, especially filter drivers, might not create device objects for some devices. If an <i>EvtDriverDeviceAdd</i> callback function does not create a device object, it must still return STATUS_SUCCESS unless an error was encountered.

If a driver's <i>EvtDriverDeviceAdd</i> callback function creates a device object but does not return STATUS_SUCCESS, the framework deletes the device object and its child devices.

If a function driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the I/O manager does not build a device stack for the device.

If a filter driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the framework converts the return value to STATUS_SUCCESS, and the I/O manager builds the device stack without the filter driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdriver.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DRIVER_DEVICE_ADD callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>