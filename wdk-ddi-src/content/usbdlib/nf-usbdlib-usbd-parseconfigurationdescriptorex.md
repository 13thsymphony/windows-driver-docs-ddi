---
UID: NF.usbdlib.USBD_ParseConfigurationDescriptorEx
title: USBD_ParseConfigurationDescriptorEx
author: windows-driver-content
description: The USBD_ParseConfigurationDescriptorEx routine searches a given configuration descriptor and returns a pointer to an interface that matches the given search criteria.
old-location: buses\usbd_parseconfigurationdescriptorex.htm
old-project: usbref
ms.assetid: c14b3cde-b501-4d07-96ae-f0e0e6320966
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USBD_ParseConfigurationDescriptorEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_ParseConfigurationDescriptorEx
req.alt-loc: Usbd.lib,Usbd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbd.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# USBD_ParseConfigurationDescriptorEx function



## -description
<p>The <b>USBD_ParseConfigurationDescriptorEx</b> routine searches a given configuration descriptor and returns a pointer to an interface that matches the given search criteria.</p>


## -syntax

````
PUSB_INTERFACE_DESCRIPTOR USBD_ParseConfigurationDescriptorEx(
  _In_ PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _In_ PVOID                         StartPosition,
  _In_ LONG                          InterfaceNumber,
  _In_ LONG                          AlternateSetting,
  _In_ LONG                          InterfaceClass,
  _In_ LONG                          InterfaceSubClass,
  _In_ LONG                          InterfaceProtocol
);
````


## -parameters
<dl>

### -param ConfigurationDescriptor [in]

<dd>
<p>Pointer to a USB configuration descriptor that contains the interface for which to search.</p>
</dd>

### -param StartPosition [in]

<dd>
<p>Pointer to the address within the configuration descriptor, provided at <i>ConfigurationDescriptor</i>, to begin searching from. To search from the beginning of the configuration descriptor, the parameters <i>ConfigurationDescriptor</i> and <i>StartPosition</i> must be the same address.</p>
</dd>

### -param InterfaceNumber [in]

<dd>
<p>Specifies the device-defined index of the interface to be retrieved. This should be set to -1 if it should not be a search criterion.</p>
</dd>

### -param AlternateSetting [in]

<dd>
<p>Specifies the device-defined alternate-setting index of the interface to be retrieved. If the caller does not wish the alternate setting value to be a search criterion, this parameter should be set to -1.</p>
</dd>

### -param InterfaceClass [in]

<dd>
<p>Specifies the device- or USB-defined identifier for the interface class of the interface to be retrieved. If the caller does not wish the interface class value to be a search criterion, this parameter should be set to -1.</p>
</dd>

### -param InterfaceSubClass [in]

<dd>
<p>Specifies the device- or USB-defined identifier for the interface subclass of the interface to be retrieved. If the caller does not wish the interface subclass value to be a search criterion, this parameter should be set to -1.</p>
</dd>

### -param InterfaceProtocol [in]

<dd>
<p>Specifies the device- or USB-defined identifier for the interface protocol of the interface to be retrieved. If the caller does not wish the interface protocol value to be a search criterion, this parameter should be set to -1.</p>
</dd>
</dl>

## -returns
<p><b>USBD_ParseConfigurationDescriptorEx</b> returns a pointer to the first interface descriptor that matches the given search criteria. If no interface matches the search criteria, it returns <b>NULL</b>.</p>

## -remarks
<p>Callers can specify more than one of the search criteria (InterfaceNumber, AlternateSetting, InterfaceClass, InterfaceSubClass, and InterfaceProtocol) when using this routine to find an interface within a configuration descriptor. For example code, see <a href="..\usbdlib\nf-usbdlib-usbd-createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>.</p>

<p>When this routine parses the configuration descriptor looking for the interface descriptor that matches the search criteria, it returns the first match, terminating the search. Callers should specify as many search criteria as are necessary to find the desired interface.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbdlib.h (include Usbdlib.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Usbd.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbspec\ns-usbspec--usb-configuration-descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>
</dt>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ParseConfigurationDescriptorEx routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
