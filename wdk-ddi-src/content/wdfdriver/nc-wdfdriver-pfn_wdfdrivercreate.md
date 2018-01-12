---
UID: NC:wdfdriver.PFN_WDFDRIVERCREATE
title: PFN_WDFDRIVERCREATE function
author: windows-driver-content
description: The WdfDriverCreate method creates a framework driver object for the calling driver.
old-location: wdf\wdfdrivercreate.htm
old-project: wdf
ms.assetid: 2b8cea0f-bca0-4ffa-834b-d7c079cf93d8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFDRIVERCREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDriverCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChangeQueueState, DriverAttributeChanged, DriverCreate, KmdfIrql, KmdfIrql2, MiniportOnlyWdmDevice
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_DPC_CONFIG, WDF_DPC_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFDRIVERCREATE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverCreate</b> method creates a framework driver object for the calling driver.



## -syntax

````
NTSTATUS WdfDriverCreate(
  _In_      PDRIVER_OBJECT         DriverObject,
  _In_      PCUNICODE_STRING       RegistryPath,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES DriverAttributes,
  _In_      PWDF_DRIVER_CONFIG     DriverConfig,
  _Out_opt_ WDFDRIVER              *Driver
);
````


## -parameters

### -param DriverObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure that represents a Windows Driver Model (WDM) driver object. The driver receives this pointer as input to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine.


### -param RegistryPath [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the registry path string that the driver received as input to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. 


### -param DriverAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param DriverConfig [in]

A pointer to a caller-allocated <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure.


### -param Driver [out, optional]

A pointer to a location that receives a handle to the new framework driver object. This parameter is optional and can be WDF_NO_HANDLE.


## -returns
<b>WdfDriverCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_DRIVER_INTERNAL_ERROR</b></dt>
</dl>The driver called <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> more than once.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A <a href="wdf.using_kernel_mode_driver_framework_with_non_pnp_drivers">non-Plug and Play (PnP) driver</a> specified an <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

 

For more information about return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the <i>DriverObject</i>, <i>RegistryPath</i>, or <i>DriverConfig</i> parameter is <b>NULL</b>.


## -remarks
A driver that uses Kernel-Mode Driver Framework must call <b>WdfDriverCreate</b> from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, before calling any other framework routines. For more information about <b>DriverEntry</b>, see <b>DriverEntry for Framework-based Drivers</b>. 

Before your driver calls <b>WdfDriverCreate</b>, the driver must call <a href="..\wdfdriver\nf-wdfdriver-wdf_driver_config_init.md">WDF_DRIVER_CONFIG_INIT</a> to initialize its <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure.

The framework driver object is the top of your driver's tree of framework objects and therefore does not have a parent object.

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the driver object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

The following code example is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine that initializes a WDF_DRIVER_CONFIG structure and then creates a framework driver object.


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
<dt>Wdfdriver.h (include Wdf.h)</dt>
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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975067">ChangeQueueState</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544951">DriverAttributeChanged</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975092">MiniportOnlyWdmDevice</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdf_driver_config_init.md">WDF_DRIVER_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverCreate method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

