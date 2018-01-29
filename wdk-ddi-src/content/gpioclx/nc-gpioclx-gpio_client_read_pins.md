---
UID : NC:gpioclx.GPIO_CLIENT_READ_PINS
title : GPIO_CLIENT_READ_PINS
author : windows-driver-content
description : The CLIENT_ReadGpioPins event callback function reads a set of general-purpose I/O (GPIO) pins that are configured as data inputs.
old-location : gpio\client_readgpiopins.htm
old-project : GPIO
ms.assetid : FE1AB8D5-DEA7-47BE-921E-BB33BBB61AC9
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GPIO.client_readgpiopins, CLIENT_ReadGpioPins callback function [Parallel Ports], CLIENT_ReadGpioPins, GPIO_CLIENT_READ_PINS, GPIO_CLIENT_READ_PINS, gpioclx/CLIENT_ReadGpioPins
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---


# GPIO_CLIENT_READ_PINS callback function
The <i>CLIENT_ReadGpioPins</i> event callback function reads a set of general-purpose I/O (GPIO) pins that are configured as data inputs.

## Syntax

```
GPIO_CLIENT_READ_PINS GpioClientReadPins;

NTSTATUS GpioClientReadPins(
  PVOID Context,
  PGPIO_READ_PINS_PARAMETERS ReadParameters
)
{...}
```

## Parameters

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`ReadParameters`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698255">GPIO_READ_PINS_PARAMETERS</a> structure that, on entry, describes the GPIO pins to read, and, on exit, contains the data that was read from the GPIO pins.


## Return Value

The <i>CLIENT_ReadGpioPins</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

This callback function is implemented by the GPIO controller driver. GpioClx calls this function.

All of the pins in the <i>PinNumberTable</i> array belong to the bank identified by the <i>BankId</i> parameter.

To register your driver's <i>CLIENT_ReadGpioPins</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ReadGpioPins</i> function pointer.

The <i>CLIENT_ReadGpioPins</i> function can be called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_ReadGpioPins</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698255">GPIO_READ_PINS_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ReadGpioPins callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>