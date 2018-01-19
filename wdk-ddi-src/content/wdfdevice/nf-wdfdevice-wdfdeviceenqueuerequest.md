---
UID : NF:wdfdevice.WdfDeviceEnqueueRequest
title : WdfDeviceEnqueueRequest function
author : windows-driver-content
description : The WdfDeviceEnqueueRequest method delivers a specified I/O request to the framework, so that the framework can subsequently add the request to one of the I/O queues that the driver has created for the specified device.
old-location : wdf\wdfdeviceenqueuerequest.htm
old-project : wdf
ms.assetid : f669790f-0370-46a0-ba38-05e35cdf23b3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceEnqueueRequest
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
req.alt-api : WdfDeviceEnqueueRequest
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <= DISPATCH_LEVEL (See remarks section)
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceEnqueueRequest function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceEnqueueRequest</b> method delivers a specified I/O request to the framework, so that the framework can subsequently add the request to one of the I/O queues that the driver has created for the specified device.

## Syntax

````
NTSTATUS WdfDeviceEnqueueRequest(
  _In_ WDFDEVICE  Device,
  _In_ WDFREQUEST Request
);
````

## Parameters

`Device`

A handle to a framework device object.

`Request`

A handle to a framework request object.


## Return Value

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The amount of available memory is low.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The driver has not created any I/O queues for the device, and the driver is not a filter driver.

<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>The device's I/O queue is not accepting requests.

 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver can call <b>WdfDeviceEnqueueRequest</b> only from an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function.

The <b>WdfDeviceEnqueueRequest</b> method adds the request to the driver's request-type-specific I/O queue for the device, if the driver has created one. Otherwise the method adds the request to the device's default queue, if the driver has created one.

If the driver has not created any I/O queues for the device, <b>WdfDeviceEnqueueRequest</b> does the following:

If the driver is a filter driver, <b>WdfDeviceEnqueueRequest</b> sends the request to the driver's I/O target.

If the driver is not a filter driver, <b>WdfDeviceEnqueueRequest</b> returns STATUS_INVALID_DEVICE_REQUEST.

While <b>WdfDeviceEnqueueRequest</b> is executing, it is possible for the driver to receive and complete or cancel the request.

As a result, if the driver needs to use the request or its context after calling <b>WdfDeviceEnqueueRequest</b>, then it should take a reference on the request before calling <b>WdfDeviceEnqueueRequest</b>.

To do so, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> before and then <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a> after the call to <b>WdfDeviceEnqueueRequest</b>. The driver must dereference the request before exiting <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a>.

For more information about the <b>WdfDeviceEnqueueRequest</b> method, see <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

For versions 1.0 and 1.5 of KMDF, <b>WdfDeviceEnqueueRequest</b> must be called at PASSIVE_LEVEL. For versions 1.7 and later, <b>WdfDeviceEnqueueRequest</b> can be called at IRQL &lt;= DISPATCH_LEVEL.

The following code example is an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function that looks for requests that contain the custom I/O control code, IOCTL_NONPNP_METHOD_NEITHER. If the I/O control code is not found, the callback function just returns the request to the framework. If the callback function finds the I/O control code, it preprocesses the request and then returns it to the framework. If an error is encountered, the callback function completes the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL (See remarks section) |
| **DDI compliance rules** | DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal |

## See Also

<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceEnqueueRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>