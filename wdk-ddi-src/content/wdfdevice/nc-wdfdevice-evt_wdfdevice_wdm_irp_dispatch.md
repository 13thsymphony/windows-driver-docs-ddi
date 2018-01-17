---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_DISPATCH
title: EVT_WDFDEVICE_WDM_IRP_DISPATCH function
author: windows-driver-content
description: A driver's EvtDeviceWdmIrpDispatch event callback function receives an IRP before the framework processes the IRP.
old-location: wdf\evtdevicewdmirpdispatch.htm
old-project: wdf
ms.assetid: C6BED59F-066E-42F6-86AE-B0423E0E847F
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDFDEVICE_WDM_IRP_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.17
req.alt-api: EvtDeviceWdmIrpDispatch
req.alt-loc: Wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDFDEVICE_WDM_IRP_DISPATCH function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceWdmIrpDispatch</i> event callback function receives an IRP before the framework processes the IRP.



## -syntax

````
EVT_WDFDEVICE_WDM_IRP_DISPATCH EvtDeviceWdmIrpDispatch;

NTSTATUS EvtDeviceWdmIrpDispatch(
  _In_    WDFDEVICE  Device,
  _In_    UCHAR      MajorFunction,
  _In_    UCHAR      MinorFunction,
  _In_    ULONG      Code,
  _In_    WDFCONTEXT DriverContext,
  _Inout_ PIRP       Irp,
  _In_    WDFCONTEXT DispatchContext
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param MajorFunction [in]

One of the IRP major function codes that are defined in wdm.h.


### -param MinorFunction [in]

One of the I/O IRP minor function codes that are defined in wdm.h for the <i>MajorFunction</i> code.


### -param Code [in]

Specifies an I/O control code value.  This parameter is valid only if <i>MajorFunction</i> is set to IRP_MJ_DEVICE_CONTROL.


### -param DriverContext [in]

An untyped pointer to driver-defined context information that the driver provided when it called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>.


### -param Irp [in, out]

A pointer to an IRP structure.


### -param DispatchContext [in]

An untyped pointer to the framework's dispatch  context information. The driver must provide this parameter when it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a>.


## -returns
The <i>EvtDeviceWdmIrpDispatch</i> callback function must:

<b>KMDF only</b>

<b>KMDF only</b>

<b>KMDF only</b>


## -remarks
The <i>EvtDeviceWdmIrpDispatch</i> callback function should only be used to select a specific queue for an IRP. To do so, the driver calls the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a> method from within the callback function.

If, after examining an IRP in this callback function, the driver does not  know how to dispatch the IRP, the driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a> to return the IRP to the framework for default handling.

A UMDF driver must call either <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a> or <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a> from this callback function.  A KMDF driver has the additional option of calling neither, and instead completing the IRP or marking it pending.

To register an <i>EvtDeviceWdmIrpDispatch</i> callback function, your driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>.

In its <i>EvtDeviceWdmIrpDispatch</i> callback function, a driver should not set a completion routine. If a completion routine is needed, a KMDF driver can provide a  <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function instead of <i>EvtDeviceWdmIrpDispatch</i>.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://msdn.microsoft.com/71872114-2A38-47FE-9D18-EF8923273811">Dispatching IRPs to I/O Queues</a>.

To define an <i>EvtDeviceWdmIrpDispatch</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWdmIrpDispatch</i> callback function that is named <i>MyDeviceWdmIrpDispatch</i>, use the <b>EVT_WDFDEVICE_WDM_IRP_DISPATCH</b> type as shown in this code example:

Then, implement your callback function:

The <b>EVT_WDFDEVICE_WDM_IRP_DISPATCH</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_IRP_DISPATCH</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md">WdfDeviceConfigureWdmIrpDispatchCallback</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDFDEVICE_WDM_IRP_DISPATCH callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

