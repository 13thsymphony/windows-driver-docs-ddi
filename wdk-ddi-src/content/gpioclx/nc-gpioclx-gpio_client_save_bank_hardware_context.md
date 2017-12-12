---
UID: NC.gpioclx.GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT
title: GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT
author: windows-driver-content
description: The CLIENT_SaveBankHardwareContext event callback function saves the hardware context of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_savebankhardwarecontext.htm
old-project: GPIO
ms.assetid: D2D2E231-E174-4C9F-96C3-35E744212F18
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
req.alt-api: CLIENT_SaveBankHardwareContext
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

# GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT callback



## -description
The <i>CLIENT_SaveBankHardwareContext</i> event callback function saves the hardware context of a bank of general-purpose I/O (GPIO) pins.



## -prototype

````
GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT CLIENT_SaveBankHardwareContext;

NTSTATUS CLIENT_SaveBankHardwareContext(
  _In_ PVOID                                               Context,
  _In_ PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS Parameters
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param Parameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698257">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a> structure that describes the bank of GPIO pins to save.


## -returns
The <i>CLIENT_SaveBankHardwareContext</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.


## -remarks
If a bank of GPIO pins supports component-level power management, GpioClx can switch the bank to a low-power Fx state if the bank is idle. If the GPIO controller bank loses its hardware context in the Fx state, the GPIO controller driver must save this context before the F0-to-Fx transition, and, later, restore the context after the Fx-to-F0 transition. Currently, F1 is the only low-power state that is defined for GPIO controllers that use GpioClx.

GpioClx calls the <i>CLIENT_SaveBankHardwareContext</i> function to save the bank's hardware context. Later, GpioClx calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a> event callback function to restore the previously saved context.

Some GPIO controller devices enable selected banks of pins to be turned on and off independently of other banks in the same device. Thus, power can be saved by turning off a bank that is idle.

To register your driver's <i>CLIENT_SaveBankHardwareContext</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_SaveBankHardwareContext</i> function pointer.

GpioClx calls the <i>CLIENT_SaveBankHardwareContext</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_SaveBankHardwareContext</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

To define a <i>CLIENT_SaveBankHardwareContext</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_SaveBankHardwareContext</i> callback function that is named <code>MyEvtGpioSaveBankHardwareContext</code>, use the GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT function type, as shown in this code example:

Then, implement your callback function as follows:

The GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.


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
Supported starting with Windows 8.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698257">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_SaveBankHardwareContext callback function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

