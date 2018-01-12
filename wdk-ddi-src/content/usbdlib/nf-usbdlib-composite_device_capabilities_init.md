---
UID: NF:usbdlib.COMPOSITE_DEVICE_CAPABILITIES_INIT
title: COMPOSITE_DEVICE_CAPABILITIES_INIT function
author: windows-driver-content
description: The COMPOSITE_DEVICE_CAPABILITIES_INIT macro initializes the COMPOSITE_DEVICE_CAPABILITIES structure.
old-location: buses\composite_driver_capabilities_init.htm
old-project: usbref
ms.assetid: 92DDF65E-4B5B-443A-9C90-3B1BB2DD3CAF
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: COMPOSITE_DEVICE_CAPABILITIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: COMPOSITE_DEVICE_CAPABILITIES_INIT
req.alt-loc: Usbdex.lib,Usbdex.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbdex.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# COMPOSITE_DEVICE_CAPABILITIES_INIT function



## -description
The <b>COMPOSITE_DEVICE_CAPABILITIES_INIT</b> macro initializes the <a href="..\usbdlib\ns-usbdlib-_composite_device_capabilities.md">COMPOSITE_DEVICE_CAPABILITIES</a> structure.



## -syntax

````
void COMPOSITE_DEVICE_CAPABILITIES_INIT(
   PCOMPOSITE_DEVICE_CAPABILITIES CapabilityFlags
);
````


## -parameters

### -param CapabilityFlags 

 A pointer to a caller-allocated <a href="..\usbdlib\ns-usbdlib-_composite_device_capabilities.md">COMPOSITE_DEVICE_CAPABILITIES</a> structure to be initialized. The macro sets the <b>CompositeDriverCapabilityFunctionSuspend</b>
member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 0.


## -returns
This routine does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbdlib.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Usbdex.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\usbdlib\ns-usbdlib-_composite_device_capabilities.md">COMPOSITE_DEVICE_CAPABILITIES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>
</dt>
<dt>
<a href="..\usbdlib\ns-usbdlib-_register_composite_device.md">REGISTER_COMPOSITE_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20COMPOSITE_DEVICE_CAPABILITIES_INIT routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

