---
UID : NC:gpioclx.GPIO_CLIENT_WRITE_PINS_MASK
title : GPIO_CLIENT_WRITE_PINS_MASK
author : windows-driver-content
description : The CLIENT_WriteGpioPinsUsingMask event callback function writes to a set of general-purpose I/O (GPIO) pins that are configured as data outputs.
old-location : gpio\client_writegpiopinsusingmask.htm
old-project : GPIO
ms.assetid : 6B3667AA-4658-4EDE-A8E1-925064BCD249
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : gpioclx.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Supported starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CLIENT_WriteGpioPinsUsingMask
req.alt-loc : Gpioclx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks.
req.typenames : "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO"
---


# GPIO_CLIENT_WRITE_PINS_MASK callback function
The <i>CLIENT_WriteGpioPinsUsingMask</i> event callback function writes to a set of general-purpose I/O (GPIO) pins that are configured as data outputs.

## Syntax

```
GPIO_CLIENT_WRITE_PINS_MASK GpioClientWritePinsMask;

NTSTATUS GpioClientWritePinsMask(
  PVOID Context,
  PGPIO_WRITE_PINS_MASK_PARAMETERS WriteParameters
)
{...}
```

## Parameters

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`WriteParameters`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698258">GPIO_WRITE_PINS_MASK_PARAMETERS</a> structure that describes a bank of GPIO pins and that contains the data to write to these pins.


## Return Value

The <i>CLIENT_WriteGpioPinsUsingMask</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

This callback function is implemented by the GPIO controller driver. GpioClx calls this function to write to a designated set of GPIO pins.

The GPIO pins that are to be written to by this function are designated by two 64-bit masks. The first mask specifies a group of GPIO pins that are to be set to 1; a bit in this mask is 1 if the corresponding GPIO pin is to be set to 1. The second mask specifies a group of GPIO pins that are to be set to 0; a bit in this mask is 1 if the corresponding GPIO pin is to be set to 0.

To register your driver's <i>CLIENT_WriteGpioPinsUsingMask</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_WriteGpioPinsUsingMask</i> function pointer.

The <i>CLIENT_WriteGpioPinsUsingMask</i> function can be called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_WriteGpioPinsUsingMask</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

To define a <i>CLIENT_WriteGpioPinsUsingMask</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_WriteGpioPinsUsingMask</i> callback function that is named <code>MyEvtGpioWriteGpioPinsUsingMask</code>, use the GPIO_CLIENT_WRITE_PINS_MASK function type, as shown in this code example:

Then, implement your callback function as follows:

The GPIO_CLIENT_WRITE_PINS_MASK function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_WRITE_PINS_MASK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gpioclx.h |
| **Library** |  |
| **IRQL** | See Remarks. |
| **DDI compliance rules** |  |

## See Also

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698258">GPIO_WRITE_PINS_MASK_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_WriteGpioPinsUsingMask callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>