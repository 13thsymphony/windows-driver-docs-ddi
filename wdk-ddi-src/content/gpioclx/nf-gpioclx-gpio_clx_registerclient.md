---
UID: NF:gpioclx.GPIO_CLX_RegisterClient
title: GPIO_CLX_RegisterClient function
author: windows-driver-content
description: The GPIO_CLX_RegisterClient method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_registerclient.htm
old-project: GPIO
ms.assetid: C87385E0-7B3F-44DA-90D0-E644C58AB375
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_CLX_RegisterClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_CLX_RegisterClient
req.alt-loc: Msgpioclxstub.lib,Msgpioclxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Msgpioclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PGPIO_CONNECT_IO_PINS_MODE, GPIO_CONNECT_IO_PINS_MODE
---

# GPIO_CLX_RegisterClient function



## -description
The <b>GPIO_CLX_RegisterClient</b> method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).



## -syntax

````
NTSTATUS GPIO_CLX_RegisterClient(
  _In_    WDFDRIVER                        Driver,
  _Inout_ PGPIO_CLIENT_REGISTRATION_PACKET RegistrationPacket,
  _In_    PUNICODE_STRING                  RegistryPath
);
````


## -parameters

### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


### -param RegistrationPacket [in, out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains the caller's registration information. This structure contains pointers to the event callback functions that the GPIO controller driver implements. Additionally, this structure specifies the size of the device context that the GPIO controller driver requires for its internal configuration data and state information.


### -param RegistryPath [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path name of the registry key for the  GPIO controller driver. This parameter should be the registry path name that was passed to the driver's <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. For more information about driver registry keys, see <a href="https://msdn.microsoft.com/74dc1889-26a9-47ba-8c8d-3cd6ed95cb68">Registry Trees for Devices and Drivers</a>.


## -returns
<b>GPIO_CLX_RegisterClient</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Driver</i>, <i>RegistrationPacket</i>, or <i>RegistryPath</i> parameter is NULL.
<dl>
<dt><b>STATUS_GPIO_INVALID_REGISTRATION_PACKET</b></dt>
</dl>The specified registration packet is not valid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Out of memory.

 


## -remarks
The GPIO controller driver calls this method to register its event callback functions with GpioClx. Typically, the driver calls this method from its <b>DriverEntry</b> routine, which runs shortly after the driver is loaded into memory.

Later, just before the GPIO controller driver unloads, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439498">GPIO_CLX_UnregisterClient</a> method to cancel its registration with GpioClx.


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
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Msgpioclxstub.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439498">GPIO_CLX_UnregisterClient</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_RegisterClient method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

