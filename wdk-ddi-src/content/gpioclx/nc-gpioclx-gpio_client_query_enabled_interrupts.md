---
UID: NC.gpioclx.GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS
title: GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS
author: windows-driver-content
description: The CLIENT_QueryEnabledInterrupts event callback function queries the state of a set of general-purpose I/O (GPIO) pins to determine which pins are both configured as interrupt inputs and enabled for interrupts.
old-location: gpio\client_queryenabledinterrupts.htm
old-project: GPIO
ms.assetid: 2F09006A-EFC6-4A38-AC5D-661DA48155FA
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.keywords: PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLIENT_QueryEnabledInterrupts
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
---

# GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS callback



## -description
The <i>CLIENT_QueryEnabledInterrupts</i> event callback function queries the state of a set of general-purpose I/O (GPIO) pins to determine which pins are both configured as interrupt inputs and enabled for interrupts.



## -prototype

````
GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS CLIENT_QueryEnabledInterrupts;

NTSTATUS CLIENT_QueryEnabledInterrupts(
  _In_ PVOID                                     Context,
  _In_ PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS QueryEnabledParameters
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param QueryEnabledParameters [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/dn265185">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a> structure. Before calling this function, the caller writes a bank ID to the <b>BankId</b> member of this structure to specify which bank of GPIO pins to query. If successful, the function writes a mask value to the <b>EnabledMask</b> member of this structure to indicate which interrupts are enabled in the specified bank.


## -returns
The <i>CLIENT_QueryEnabledInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.


## -remarks
Starting with Windows 8.1, the GPIO controller driver can, as an option, implement a <i>CLIENT_QueryEnabledInterrupts</i> callback function. If implemented, this function is called by the GPIO framework extension (GpioClx) to determine which interrupts are enabled in a bank of GPIO pins.

The <i>QueryEnabledParameters</i> parameter points to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/dn265185">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a> structure. The caller sets the value of the <b>BankId</b> member of this structure. The <i>CLIENT_QueryEnabledInterrupts</i> function writes to the <b>EnabledMask</b> member of the structure.

To register your driver's <i>CLIENT_QueryEnabledInterrupts</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_QueryEnabledInterrupts</i> function pointer.

The <i>CLIENT_QueryEnabledInterrupts</i> function is optional. If your driver does not implement this function, set the <b>CLIENT_QueryEnabledInterrupts</b> member of the <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure to <b>NULL</b>.

If the <i>CLIENT_QueryEnabledInterrupts</i> function is implemented, GpioClx uses this function to improve driver reliability and diagnostics. GpioClx calls this function to verify that the set of interrupts enabled at the GPIO controller matches what GpioClx expects. Typically, a mismatch indicates a driver bug that can potentially cause an interrupt storm. GpioClx uses this function to do more extensive state validation in checked (debug) builds, and reduces the number of calls to this function in free (retail) builds to avoid impacting performance. If implemented, this function must directly read the hardware state instead of reading a cached or software-maintained version of the state.

GpioClx calls the <i>CLIENT_QueryEnabledInterrupts</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_QueryEnabledInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

To define a <i>CLIENT_QueryEnabledInterrupts</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_QueryEnabledInterrupts</i> callback function that is named <code>MyEvtGpioQueryEnabledInterrupts</code>, use the GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type, as shown in this code example:

Then, implement your callback function as follows:

The GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.


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
Supported starting with Windows 8.1.

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
IRQL

</th>
<td width="70%">
See Remarks.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265185">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_QueryEnabledInterrupts callback function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

