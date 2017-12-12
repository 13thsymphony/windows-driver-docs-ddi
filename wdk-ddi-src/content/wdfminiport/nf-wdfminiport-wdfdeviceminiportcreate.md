---
UID: NF.wdfminiport.WdfDeviceMiniportCreate
title: WdfDeviceMiniportCreate function
author: windows-driver-content
description: The WdfDeviceMiniportCreate method creates a framework device object that a miniport driver can use.
old-location: wdf\wdfdeviceminiportcreate.htm
old-project: wdf
ms.assetid: d74dedbd-f418-4ea3-ae76-c0da9c5f2fb9
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfDeviceMiniportCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceMiniportCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceMiniportCreate function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceMiniportCreate</b> method creates a framework device object that a miniport driver can use.



## -syntax

````
NTSTATUS WdfDeviceMiniportCreate(
  _In_     WDFDRIVER              Driver,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _In_     PDEVICE_OBJECT         DeviceObject,
  _In_opt_ PDEVICE_OBJECT         AttachedDeviceObject,
  _In_opt_ PDEVICE_OBJECT         Pdo,
  _Out_    WDFDEVICE              *Device
);
````


## -parameters

### -param Driver [in]

A handle to the driver's framework driver object, obtained by a previous call to <a href="wdf.wdfdrivercreate">WdfDriverCreate</a>.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param DeviceObject [in]

A pointer to a WDM <a href="kernel.device_object">DEVICE_OBJECT</a> structure that represents the functional device object (FDO) for the miniport driver.


### -param AttachedDeviceObject [in, optional]

A pointer to a WDM DEVICE_OBJECT structure that represents the next-lower device object in the device stack.


### -param Pdo [in, optional]

A pointer to a WDM DEVICE_OBJECT structure that represents the physical device object (PDO) for the device.


### -param Device [out]

A pointer to a location that receives a handle to the new framework device object.


## -returns
If the <b>WdfDeviceMiniportCreate</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A device object could not be allocated.

 

For a list of other return values that <b>WdfDeviceMiniportCreate</b> can return, see <a href="wdf.framework_object_creation_errors">Framework Object Creation Errors</a>.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If your miniport driver uses the framework, the miniport driver should call <b>WdfDeviceMiniportCreate</b> when its port driver informs it that a device is available. Miniport drivers do not call <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>.

Your miniport driver might receive its <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers from its port driver. For example, an NDIS miniport driver can obtain these pointers by calling <a href="netvista.ndismgetdeviceproperty">NdisMGetDeviceProperty</a>.

The following restrictions apply to framework device objects that a miniport driver obtains by calling <b>WdfDeviceMiniportCreate</b>:

The device that the device object represents must support Plug and Play.

The device object does not support any of the device object's event callback functions. Therefore, the port driver must handle all Plug and Play (PnP) and power management operations. 

The device object handle cannot be passed to <a href="wdf.wdfwmiprovidercreate">WdfWmiProviderCreate</a>, so the port driver must provide any required support for Windows Management Instrumentation (WMI).

The device object handle cannot be passed to <a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a>, so the framework does not support I/O queues for miniport drivers.

The device object handle cannot be passed to <a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>, so the framework does not support interrupt objects for miniport drivers.

The device object handle cannot be passed to any general framework device object methods except <a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>, <a href="wdf.wdfdevicewdmgetdeviceobject">WdfDeviceWdmGetDeviceObject</a>, <a href="wdf.wdfdevicewdmgetattacheddevice">WdfDeviceWdmGetAttachedDevice</a>, and <a href="wdf.wdfdevicewdmgetphysicaldevice">WdfDeviceWdmGetPhysicalDevice</a>.

The device object handle cannot be passed to any <a href="wdf_device_object_reference.htm#fdo_methods">framework FDO methods</a> except <a href="wdf.wdffdoqueryforinterface">WdfFdoQueryForInterface</a>.

The device object handle cannot be passed to any <a href="wdf_device_object_reference.htm#pdo_methods">framework PDO methods</a> or to <a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>, so the miniport driver cannot be a bus driver.

The driver must eventually call <a href="wdf.wdfobjectdelete">WdfObjectDelete</a> to delete the device object that <b>WdfDeviceMiniportCreate</b> creates.

Framework device objects that <b>WdfDeviceMiniportCreate</b> create can be used as a parent object for any subsequently created framework object. 

In order to send I/O requests to I/O targets, the miniport driver might pass the device object handle to <a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>, <a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>, or <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

The miniport driver can pass the device object handle to <a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a> if the device supports DMA operations.

For more information about miniport drivers, see <a href="wdf.creating_kmdf_miniport_drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.

The following code example calls <a href="netvista.ndismgetdeviceproperty">NdisMGetDeviceProperty</a> to obtain <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers; initializes the device object's context space, and creates a miniport device object. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfminiport.h (include Wdfminiport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>
</dt>
<dt>
<a href="wdf.wdfdriverminiportunload">WdfDriverMiniportUnload</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceMiniportCreate method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

