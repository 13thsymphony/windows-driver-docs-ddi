---
UID : NF:wdfcontrol.WdfControlDeviceInitSetShutdownNotification
title : WdfControlDeviceInitSetShutdownNotification function
author : windows-driver-content
description : The WdfControlDeviceInitSetShutdownNotification method sets shutdown notification information for a control device object.
old-location : wdf\wdfcontroldeviceinitsetshutdownnotification.htm
old-project : wdf
ms.assetid : 43a5a017-f5de-4906-acbb-96419b4a3f1c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfcontroldeviceinitsetshutdownnotification, WdfControlDeviceInitSetShutdownNotification method, wdf.wdfcontroldeviceinitsetshutdownnotification, WdfControlDeviceInitSetShutdownNotification, wdfcontrol/WdfControlDeviceInitSetShutdownNotification, PFN_WDFCONTROLDEVICEINITSETSHUTDOWNNOTIFICATION, DFDeviceObjectControllerDevObjRef_ee736de4-6e27-46d9-8f83-40d7368c960a.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfcontrol.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : ControlDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
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
req.typenames : WDF_DEVICE_SHUTDOWN_FLAGS
req.product : Windows 10 or later.
---


# WdfControlDeviceInitSetShutdownNotification function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfControlDeviceInitSetShutdownNotification</b> method sets shutdown notification information for a control device object.

## Syntax

````
VOID WdfControlDeviceInitSetShutdownNotification(
  _In_ PWDFDEVICE_INIT                      DeviceInit,
  _In_ PFN_WDF_DEVICE_SHUTDOWN_NOTIFICATION Notification,
  _In_ UCHAR                                Flags
);
````

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained by calling <a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a>.

`Notification`

A pointer to the driver's <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> event callback function.

`Flags`

One or more <a href="..\wdfcontrol\ne-wdfcontrol-_wdf_device_shutdown_flags.md">WDF_DEVICE_SHUTDOWN_FLAGS</a>-typed flags that indicate when the <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> callback function will be called.


## Return Value

None

## Remarks

The driver must call <b>WdfControlDeviceInitSetShutdownNotification</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfControlDeviceInitSetShutdownNotification</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfcontrol.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | ControlDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfcontrol\ne-wdfcontrol-_wdf_device_shutdown_flags.md">WDF_DEVICE_SHUTDOWN_FLAGS</a>

<a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfControlDeviceInitSetShutdownNotification method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>