---
UID: NF:wdfusb.WdfUsbInterfaceSelectSetting
title: WdfUsbInterfaceSelectSetting function
author: windows-driver-content
description: The WdfUsbInterfaceSelectSetting method selects a specified alternate setting for a specified USB interface.
old-location: wdf\wdfusbinterfaceselectsetting.htm
old-project: wdf
ms.assetid: 398b7649-152e-4fed-b633-16627dadf0f8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfUsbInterfaceSelectSetting
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbInterfaceSelectSetting
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbInterfaceSelectSetting function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceSelectSetting</b> method selects a specified alternate setting for a specified USB interface.



## -syntax

````
NTSTATUS WdfUsbInterfaceSelectSetting(
  _In_     WDFUSBINTERFACE                          UsbInterface,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES                   PipesAttributes,
  _In_     PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS Params
);
````


## -parameters

### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


### -param PipesAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for pipe objects that the framework creates for the interface. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Params [in]

A pointer to a caller-supplied <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure that contains interface selection parameters.


## -returns
<b>WdfUsbInterfaceSelectSetting</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory to create a new pipe object.

 

For a list of other return values that the <b>WdfUsbInterfaceSelectSetting</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
After your driver calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> to select a configuration, the driver can call <b>WdfUsbInterfaceSelectSetting</b> to select an alternate setting for one of the device's interfaces.

Your driver can select an interface's alternate setting by specifying a USB interface descriptor or a <a href="..\usb\ns-usb-_urb.md">URB</a>, or by just providing an alternate setting for the interface. In all cases, the driver must provide a handle to an interface object. 

If your driver just provides an alternate setting, the framework uses the interface object to determine the interface to which the setting belongs. 

If your driver specifies an interface descriptor or a URB, the framework uses the interface that is specified in the descriptor or URB.

The framework creates a framework USB pipe object for each pipe that is associated with the interface, after deleting any pipe objects that the framework might have previously created for the interface. To obtain information about an interface's pipe objects, your driver can call <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md">WdfUsbInterfaceGetNumConfiguredPipes</a> and <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.

For more information about the <b>WdfUsbInterfaceSelectSetting</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure with attributes for the pipe objects that the framework will create. Then, the example initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure to specify alternate setting 1. Finally, the example calls <b>WdfUsbInterfaceSelectSetting</b> to select the alternate setting and create pipe objects for the interface's pipes.


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
<dt>Wdfusb.h (include Wdfusb.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554042">UsbKmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh995019">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>
</dt>
<dt>
<a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md">WdfUsbInterfaceGetNumConfiguredPipes</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceSelectSetting method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

