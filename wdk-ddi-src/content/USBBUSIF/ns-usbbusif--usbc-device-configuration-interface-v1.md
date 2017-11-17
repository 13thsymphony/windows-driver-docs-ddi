---
UID: NS.usbbusif._USBC_DEVICE_CONFIGURATION_INTERFACE_V1
title: USBC_DEVICE_CONFIGURATION_INTERFACE_V1
author: windows-driver-content
description: The USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure is exposed by the vendor-supplied filter drivers to assist the USB generic parent driver in defining interface collections.
old-location: buses\usbc_device_configuration_interface_v1.htm
ms.assetid: 86e8946f-f87f-40d4-bd02-6e4befe847e0
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: usbref
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBC_DEVICE_CONFIGURATION_INTERFACE_V1
req.alt-loc: usbbusif.h
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
ms.keywords: USBC_DEVICE_CONFIGURATION_INTERFACE_V1, USBC_DEVICE_CONFIGURATION_INTERFACE_V1, *PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1
req.iface: 
req.product: Windows 10 or later.
---

# USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure



## -description
<p>The <b>USBC_DEVICE_CONFIGURATION_INTERFACE_V1</b> structure is exposed by the vendor-supplied filter drivers to assist the USB generic parent driver in defining interface collections.</p>


## -syntax

````
typedef struct _USBC_DEVICE_CONFIGURATION_INTERFACE_V1 {
  USHORT                     Size;
  USHORT                     Version;
  PVOID                      Context;
  PINTERFACE_REFERENCE       InterfaceReference;
  PINTERFACE_DEREFERENCE     InterfaceDereference;
  USBC_START_DEVICE_CALLBACK StartDeviceCallback;
  USBC_PDO_ENABLE_CALLBACK   PdoEnableCallback;
  PVOID                      Reserved[8];
} USBC_DEVICE_CONFIGURATION_INTERFACE_V1, *PUSBC_DEVICE_CONFIGURATION_INTERFACE_V1;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size, in bytes, of this structure.</p>
</dd>

### -field <b>Version</b>

<dd>
<p>The version of the interface.</p>
</dd>

### -field <b>Context</b>

<dd>
<p>The USB generic parent driver does not use this member. It is populated by the vendor supplied filter driver and may be used to track instance information for the bus interface. It is passed as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>. </p>
</dd>

### -field <b>InterfaceReference</b>

<dd>
<p>Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>. </p>
</dd>

### -field <b>InterfaceDereference</b>

<dd>
<p>Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>. </p>
</dd>

### -field <b>StartDeviceCallback</b>

<dd>
<p>Pointer to the callback routine that the filter driver furnishes to the USB generic parent driver to assist in defining interface collections on a device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539007">USBC_START_DEVICE_CALLBACK</a>.</p>
</dd>

### -field <b>PdoEnableCallback</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbbusif.h (include Usbbusif.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3cf4e9f2-ea33-491f-94af-62d2afacc899">Customizing Enumeration of Interface Collections for Composite Devices</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539007">USBC_START_DEVICE_CALLBACK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBC_DEVICE_CONFIGURATION_INTERFACE_V1 structure%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
