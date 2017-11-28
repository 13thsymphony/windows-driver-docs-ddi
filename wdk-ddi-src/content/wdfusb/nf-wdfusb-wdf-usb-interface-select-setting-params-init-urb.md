---
UID: NF.wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
author: windows-driver-content
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a URB.
old-location: wdf\wdf_usb_interface_select_setting_params_init_urb.htm
old-project: wdf
ms.assetid: 0c11941e-d0fc-4b0f-bf18-9920d371dd09
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
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
req.alt-api: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
req.alt-loc: wdfusb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying a URB.</p>


## -syntax

````
VOID WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB(
  _Out_ PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS Params,
  _In_  PURB                                     Urb
);
````


## -parameters
<dl>

### -param <i>Params</i> [out]

<dd>
<p>A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.</p>
</dd>

### -param <i>Urb</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the value that is specified by <i>Urb</i> pointer.</p>

<p>To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553008">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553011">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>
</p>

<p><b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b></p>

<p>The following code example initializes a URB structure and then uses the structure as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550073">WdfUsbInterfaceSelectSetting</a>.</p>

<p>The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the value that is specified by <i>Urb</i> pointer.</p>

<p>To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553008">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553011">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>
</p>

<p><b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b></p>

<p>The following code example initializes a URB structure and then uses the structure as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550073">WdfUsbInterfaceSelectSetting</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553008">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553011">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
