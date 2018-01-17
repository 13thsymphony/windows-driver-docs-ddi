---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SURPRISE_REMOVAL
title: EVT_WDF_DEVICE_SURPRISE_REMOVAL function
author: windows-driver-content
description: A driver's EvtDeviceSurpriseRemoval event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that the device has failed.
old-location: wdf\evtdevicesurpriseremoval.htm
old-project: wdf
ms.assetid: 0fa0eb7e-7fbb-4838-b1d7-ef5a9d5024d4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_DEVICE_SURPRISE_REMOVAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtDeviceSurpriseRemoval
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
req.irql: PASSIVE_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_SURPRISE_REMOVAL function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSurpriseRemoval</i> event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that <a href="wdf.reporting_device_failures">the device has failed</a>.



## -syntax

````
EVT_WDF_DEVICE_SURPRISE_REMOVAL EvtDeviceSurpriseRemoval;

VOID EvtDeviceSurpriseRemoval(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
None


## -remarks
To register an <i>EvtDeviceSurpriseRemoval</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The framework does not synchronize the <i>EvtDeviceSurpriseRemoval</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://msdn.microsoft.com/be7d3c0e-c3cf-4104-ab81-5ecdcb9163c8">Using Automatic Synchronization</a>. 

For more information about when the framework calls this callback function, and for more information about synchronization issues, see <a href="https://msdn.microsoft.com/85e69401-0128-4641-aa0f-fd7c4f22f395">A User Unplugs a Device</a>.



To define an <i>EvtDeviceSurpriseRemoval</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSurpriseRemoval</i> callback function that is named <i>MyDeviceSurpriseRemoval</i>, use the <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>