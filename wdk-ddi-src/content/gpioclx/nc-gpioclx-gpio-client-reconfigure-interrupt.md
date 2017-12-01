---
UID: NC.gpioclx.GPIO_CLIENT_RECONFIGURE_INTERRUPT
title: GPIO_CLIENT_RECONFIGURE_INTERRUPT
author: windows-driver-content
description: The CLIENT_ReconfigureInterrupt event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.
old-location: gpio\client_reconfigureinterrupt.htm
old-project: GPIO
ms.assetid: 2F654D79-7DB6-45C4-8E6D-2EBAEF2DA7F5
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.keywords: PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLIENT_ReconfigureInterrupt
req.alt-loc: Gpioclx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks.
req.iface: 
---

# GPIO_CLIENT_RECONFIGURE_INTERRUPT callback



## -description
<p>The <i>CLIENT_ReconfigureInterrupt</i> event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.</p>


## -prototype

````
GPIO_CLIENT_RECONFIGURE_INTERRUPT CLIENT_ReconfigureInterrupt;

NTSTATUS CLIENT_ReconfigureInterrupt(
  _In_ PVOID                                   Context,
  _In_ PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS ReconfigureParameters
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.</p>
</dd>

### -param <i>ReconfigureParameters</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698256">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a> structure that specifies how to reconfigure the GPIO interrupt pin.</p>
</dd>
</dl>

## -returns
<p>The <i>CLIENT_ReconfigureInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.</p>

## -remarks
<p>The GPIO framework extension (GpioClx) might call the <i>CLIENT_ReconfigureInterrupt</i> function to change the interrupt mode or interrupt polarity of a GPIO pin that is used as an interrupt input.</p>

<p>For example, if the GPIO controller hardware does not directly support active-both interrupts, but can be configured to support active-high and active-low level-mode interrupts, GpioClx can emulate an active-both interrupt pin by calling the <i>CLIENT_ReconfigureInterrupt</i> function to alternately configure a GPIO pin for active-high and active-low level-mode interrupts. For more information about active-both interrupts, see the description of the <b>EmulateActiveBoth</b> flag in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>.</p>

<p>GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="NULL">Optional and Required GPIO Callback Functions</a>.</p>

<p>To define a <i>CLIENT_ReconfigureInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>CLIENT_ReconfigureInterrupt</i> callback function that is named <code>MyEvtGpioReconfigureInterrupt</code>, use the GPIO_CLIENT_RECONFIGURE_INTERRUPT function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The GPIO_CLIENT_RECONFIGURE_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_RECONFIGURE_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698256">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ReconfigureInterrupt callback function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
