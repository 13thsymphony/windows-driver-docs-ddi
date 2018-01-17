---
UID: NC:gpioclx.GPIO_CLIENT_ENABLE_INTERRUPT
title: GPIO_CLIENT_ENABLE_INTERRUPT function
author: windows-driver-content
description: The CLIENT_EnableInterrupt event callback function enables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.
old-location: gpio\client_enableinterrupt.htm
old-project: GPIO
ms.assetid: BCCD3046-A7CE-4CD7-82A5-78F0A3684BA4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_CLIENT_ENABLE_INTERRUPT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLIENT_EnableInterrupt
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
req.irql: Called at PASSIVE_LEVEL.
req.typenames: FWPS_CONNECT_REQUEST0
---

# GPIO_CLIENT_ENABLE_INTERRUPT function



## -description
The <i>CLIENT_EnableInterrupt</i> event callback function enables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.



## -syntax

````
GPIO_CLIENT_ENABLE_INTERRUPT CLIENT_EnableInterrupt;

NTSTATUS CLIENT_EnableInterrupt(
  _In_ PVOID                             Context,
  _In_ PGPIO_ENABLE_INTERRUPT_PARAMETERS InterruptParameters
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param InterruptParameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406464">GPIO_ENABLE_INTERRUPT_PARAMETERS</a> structure that specifies a GPIO pin and describes the interrupt attributes of this pin.


## -returns
The <i>CLIENT_EnableInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.


## -remarks
This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to enable interrupts on a GPIO pin that is configured as an interrupt request input.

To register your driver's <i>CLIENT_EnableInterrupt</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_EnableInterrupt</i> function pointer.

GpioClx always calls the <i>CLIENT_EnableInterrupt</i> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a> callback functions at IRQL = PASSIVE_LEVEL. However, if the GPIO registers are memory-mapped, GpioClx calls the other interrupt-related callback functions from its ISR at DIRQL. In this case, the <i>CLIENT_EnableInterrupt</i> and <i>CLIENT_DisableInterrupt</i> functions should use the GPIO interrupt lock to synchronize their interrupt-related operations to the ISR. For more information, see <a href="https://msdn.microsoft.com/D9698A50-7CC2-463C-9E46-7FE428F3193E">Interrupt Synchronization for GPIO Controller Drivers</a>.

To define a <i>CLIENT_EnableInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_EnableInterrupt</i> callback function that is named <code>MyEvtGpioEnableInterrupt</code>, use the GPIO_CLIENT_ENABLE_INTERRUPT function type, as shown in this code example:

Then, implement your callback function as follows:

The GPIO_CLIENT_ENABLE_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_ENABLE_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406464">GPIO_ENABLE_INTERRUPT_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_EnableInterrupt callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

