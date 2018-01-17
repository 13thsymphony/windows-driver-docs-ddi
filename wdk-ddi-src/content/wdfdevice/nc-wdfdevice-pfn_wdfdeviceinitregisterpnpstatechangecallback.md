---
UID: NC:wdfdevice.PFN_WDFDEVICEINITREGISTERPNPSTATECHANGECALLBACK
title: PFN_WDFDEVICEINITREGISTERPNPSTATECHANGECALLBACK function
author: windows-driver-content
description: The WdfDeviceInitRegisterPnpStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.
old-location: wdf\wdfdeviceinitregisterpnpstatechangecallback.htm
old-project: wdf
ms.assetid: a14b790a-28d7-4fb8-823f-f37f05e7529f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEINITREGISTERPNPSTATECHANGECALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceInitRegisterPnpStateChangeCallback
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# PFN_WDFDEVICEINITREGISTERPNPSTATECHANGECALLBACK function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.



## -syntax

````
NTSTATUS WdfDeviceInitRegisterPnpStateChangeCallback(
  _In_ PWDFDEVICE_INIT                              DeviceInit,
  _In_ WDF_DEVICE_PNP_STATE                         PnpState,
  _In_ PFN_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION EvtDevicePnpStateChange,
  _In_ ULONG                                        CallbackTypes
);
````


## -parameters

### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param PnpState [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a> enumerator that identifies the Plug and Play machine state for which the driver is requesting notification.


### -param EvtDevicePnpStateChange [in]

A caller-supplied pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a> event callback function.


### -param CallbackTypes [in]

An ORed combination of <a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## -returns
If the operation succeeds, <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is insufficient memory to complete the operation.

 


## -remarks
If your driver calls <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

The following code example registers an event callback function that the framework will call when the device's Plug and Play state machine changes state.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>
</dt>
<dt>
<a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>
</dt>
<dt>
<a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitRegisterPnpStateChangeCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

