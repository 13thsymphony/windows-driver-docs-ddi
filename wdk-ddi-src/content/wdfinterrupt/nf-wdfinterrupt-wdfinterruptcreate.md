---
UID: NF.wdfinterrupt.WdfInterruptCreate
title: WdfInterruptCreate function
author: windows-driver-content
description: The WdfInterruptCreate method creates a framework interrupt object.
old-location: wdf\wdfinterruptcreate.htm
old-project: wdf
ms.assetid: 6279f9ed-f271-45e6-92ef-2a919f3584ed
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfInterruptCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfInterruptCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfInterruptCreate function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptCreate</b> method creates a framework interrupt object.



## -syntax

````
NTSTATUS WdfInterruptCreate(
  _In_     WDFDEVICE              Device,
  _In_     PWDF_INTERRUPT_CONFIG  Configuration,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFINTERRUPT           *Interrupt
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Configuration [in]

A pointer to a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure that was initialized by a call to <a href="wdf.wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a>.


### -param Attributes [in, optional]

A pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework interrupt object.  (See Remarks for additional information.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Interrupt [out]

A pointer to a location that receives a handle to the new interrupt object.


## -returns
<b>WdfInterruptCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the WDF_INTERRUPT_CONFIG structure is incorrect.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
<a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a> was called after the device was started.


<a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a> also returns this value if the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EVT_WDF_DEVICE_PREPARE_HARDWARE</a> callback routine calls <b>WdfInterruptCreate</b> with   the <b>InterruptRaw</b> and <b>InterruptTranslated</b> members of the <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure set to <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory.
<dl>
<dt><b>STATUS_WDF_PARENT_ASSIGNMENT_NOT_ALLOWED</b></dt>
</dl>In KMDF version 1.9 or earlier, the driver specified a non-<b>NULL</b> value for the <b>ParentObject</b> member of the <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.

In KMDF version 1.11 or later, the driver specified a value other than a framework device or queue for the <b>ParentObject</b> member of the <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>The <b>AutomaticSerialization</b> member of the <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure is set to <b>TRUE</b> and either:

For more information, see <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The driver requested passive-level interrupt handling on a platform earlier than Windows 8.

 

For a list of other return values that the <b>WdfInterruptCreate</b> method might return, see <a href="wdf.framework_object_creation_errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Drivers typically call the  <b>WdfInterruptCreate</b> method from an <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. Starting in KMDF version 1.11 and UMDF version 2.0, drivers can call <b>WdfInterruptCreate</b> from <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDriverDeviceAdd</i>, the <b>InterruptRaw</b>  and <b>InterruptTranslated</b>  members of the <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure
must be NULL. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDevicePrepareHardware</i>, these members must both be valid.

If you are creating a wake-capable interrupt object, as described in <a href="wdf.using_an_interrupt_to_wake_a_device">Using an Interrupt to Wake a Device</a>, you must call <b>WdfInterruptCreate</b> from <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>.

 Your driver must call <b>WdfInterruptCreate</b> once for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support.

After the PnP manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that <a href="wdf.using_kernel_mode_driver_framework_with_non_pnp_drivers">do not support Plug and Play</a> cannot use interrupt objects.)

The system might not assign all of the interrupt resources that a device can support. For example, a driver would create eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.

Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's <a href="wdf.framework_object_context_space">context space</a>. The <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that the driver passes to <b>WdfInterruptCreate</b> should describe the context space.

For drivers using framework version 1.9 and earlier, the parent of each interrupt object is the device object that the interrupt belongs to. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. Beginning in version 1.11, <b>ParentObject</b> can be a framework device object or queue object. If the driver specifies a parent, the driver must set the <b>AutomaticSerialization</b> member of the configuration structure to TRUE. The driver can specify a parent for both interrupts at DIRQL and <a href="wdf.supporting_passive_level_interrupts">passive-level interrupts</a>.

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework interrupt object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.

The following code example initializes a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure and a WDF_OBJECT_ATTRIBUTES structure and then calls <b>WdfInterruptCreate</b>.


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
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfinterrupt.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

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
<a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a>
</dt>
<dt>
<a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptCreate method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

