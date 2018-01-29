---
UID : NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_DISPATCH
title : EVT_WDFDEVICE_WDM_IRP_DISPATCH
author : windows-driver-content
description : A driver's EvtDeviceWdmIrpDispatch event callback function receives an IRP before the framework processes the IRP.
old-location : wdf\evtdevicewdmirpdispatch.htm
old-project : wdf
ms.assetid : C6BED59F-066E-42F6-86AE-B0423E0E847F
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtdevicewdmirpdispatch, EvtDeviceWdmIrpDispatch callback function, EvtDeviceWdmIrpDispatch, EVT_WDFDEVICE_WDM_IRP_DISPATCH, EVT_WDFDEVICE_WDM_IRP_DISPATCH, wdfdevice/EvtDeviceWdmIrpDispatch, kmdf.evtdevicewdmirpdispatch
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.11
req.umdf-ver : 2.17
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DEVICE_SHUTDOWN_FLAGS
req.product : Windows 10 or later.
---


# EVT_WDFDEVICE_WDM_IRP_DISPATCH function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceWdmIrpDispatch</i> event callback function receives an IRP before the framework processes the IRP.

## Syntax

```
EVT_WDFDEVICE_WDM_IRP_DISPATCH EvtWdfdeviceWdmIrpDispatch;

NTSTATUS EvtWdfdeviceWdmIrpDispatch(
  WDFDEVICE Device,
  UCHAR MajorFunction,
  UCHAR MinorFunction,
  ULONG Code,
  WDFCONTEXT DriverContext,
  PIRP Irp,
  WDFCONTEXT DispatchContext
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.

`MajorFunction`

One of the IRP major function codes that are defined in wdm.h.

`MinorFunction`

One of the I/O IRP minor function codes that are defined in wdm.h for the <i>MajorFunction</i> code.

`Code`

Specifies an I/O control code value.  This parameter is valid only if <i>MajorFunction</i> is set to IRP_MJ_DEVICE_CONTROL.

`DriverContext`

An untyped pointer to driver-defined context information that the driver provided when it called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>.

`Irp`

A pointer to an IRP structure.

`DispatchContext`

An untyped pointer to the framework's dispatch  context information. The driver must provide this parameter when it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a>.


## Return Value

The <i>EvtDeviceWdmIrpDispatch</i> callback function must:
<ul>
<li>Return the value that the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a> method returns, if the callback function calls that method.</li>
<li>Return the value that the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a> method returns, if the callback function calls that method.</li>
<li>
<b>KMDF only</b></p> Set the <b>IoStatus.Status</b> member of the IRP to STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE, and return the same value (after calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) if the callback function successfully completes the received IRP.</li>
<li>
<b>KMDF only</b></p>Set the <b>IoStatus.Status</b> member of the IRP to a status value for which NT_SUCCESS(status) equals FALSE, and return the same value (after calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) if the callback function detects an error.</li>
<li>
<b>KMDF only</b></p>Return STATUS_PENDING if the callback function calls <a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>.</li>
</ul>

## Remarks

The <i>EvtDeviceWdmIrpDispatch</i> callback function should only be used to select a specific queue for an IRP. To do so, the driver calls the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a> method from within the callback function.

If, after examining an IRP in this callback function, the driver does not  know how to dispatch the IRP, the driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a> to return the IRP to the framework for default handling.

A UMDF driver must call either <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a> or <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a> from this callback function.  A KMDF driver has the additional option of calling neither, and instead completing the IRP or marking it pending.

To register an <i>EvtDeviceWdmIrpDispatch</i> callback function, your driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>.

In its <i>EvtDeviceWdmIrpDispatch</i> callback function, a driver should not set a completion routine. If a completion routine is needed, a KMDF driver can provide a  <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function instead of <i>EvtDeviceWdmIrpDispatch</i>.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.17 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDFDEVICE_WDM_IRP_DISPATCH callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>