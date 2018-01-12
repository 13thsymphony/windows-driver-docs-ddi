---
UID: NF:wdfwmi.WdfWmiInstanceCreate
title: WdfWmiInstanceCreate function
author: windows-driver-content
description: The WdfWmiInstanceCreate method creates a WMI instance object that represents an instance of a WMI data provider.
old-location: wdf\wdfwmiinstancecreate.htm
old-project: wdf
ms.assetid: ed662d6f-c42f-4dcb-86c5-135a302c59d7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfWmiInstanceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfWmiInstanceCreate
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
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceCreate function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceCreate</b> method creates a WMI instance object that represents an instance of a WMI data provider.



## -syntax

````
NTSTATUS WdfWmiInstanceCreate(
  _In_      WDFDEVICE                Device,
  _In_      PWDF_WMI_INSTANCE_CONFIG InstanceConfig,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES   InstanceAttributes,
  _Out_opt_ WDFWMIINSTANCE           *Instance
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that represents the device that the instance is being created for. The device object cannot be a <a href="wdf.using_control_device_objects">control device object</a>.


### -param InstanceConfig [in]

A pointer to a caller-initialized <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure, which contains configuration information for an instance of a WMI data provider.


### -param InstanceAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the new WMI instance object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Instance [out, optional]

A pointer to a location that receives a handle to the new WMI instance object. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfWmiInstanceCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure that the <i>InstanceConfig</i> parameter points to was incorrect.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory.
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>The driver set the <b>UseContextForQuery</b> member of the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure to <b>TRUE</b> but specified a context space size that is larger than ULONG_MAX in the <i>InstanceAttributes</i> parameter's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.

 

For a list of other return values that the <b>WdfWmiInstanceCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If a driver is creating multiple instances of a provider, the driver must call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> to create a provider object before calling <b>WdfWmiInstanceCreate</b>. The driver passes the provider object's handle to <b>WdfWmiInstanceCreate</b> by placing the handle in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure. (If the driver supplies a provider object handle, the <i>Device</i> parameter is not used and can be <b>NULL</b>.)

If the driver is creating a single instance of a provider, it does not have to call <b>WdfWmiInstanceCreate</b> before calling <b>WdfWmiInstanceCreate</b>. In this case, <b>WdfWmiInstanceCreate</b> also creates a WMI provider object. Therefore, the driver's WDF_WMI_INSTANCE_CONFIG structure must include a pointer to a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a> structure that describes the WMI data provider.

The framework instructs WMI to create a dynamic instance name, which applications can use, from the device instance ID of the driver's physical device object (PDO). (The framework does not support static instance names that Windows Driver Model (WDM) drivers set in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> structure.)

The WMI instance object's parent is the WMI provider object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

After the driver calls <b>WdfWmiInstanceCreate</b>, it can call <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a> to obtain a handle to the parent provider object and <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetdevice.md">WdfWmiInstanceGetDevice</a> to obtain a handle to the provider's device.

For more information about the <b>WdfWmiInstanceCreate</b> method, see <a href="wdf.supporting_wmi_in_kmdf_drivers">Supporting WMI in Framework-Based Drivers</a>.

If the <b>Register</b> member of the <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure that <i>InstanceConfig</i> points to is <b>TRUE</b>, <b>WdfWmiInstanceCreate</b> registers the provider instance synchronously (that is, before returning) if this method is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL &gt; PASSIVE_LEVEL. 

The following code example is from the <a href="wdf.sample_kmdf_drivers">PCIDRV</a> sample driver. This example registers a MOF resource name for a device, initializes a WDF_WMI_PROVIDER_CONFIG structure and a WDF_WMI_INSTANCE_CONFIG structure, and calls <b>WdfWmiInstanceCreate</b>.


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
<dt>Wdfwmi.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_instance_config_init_provider_config.md">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_provider_config.md">WDF_WMI_PROVIDER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdf_wmi_provider_config_init.md">WDF_WMI_PROVIDER_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignmofresourcename.md">WdfDeviceAssignMofResourceName</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetdevice.md">WdfWmiInstanceGetDevice</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceCreate method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

