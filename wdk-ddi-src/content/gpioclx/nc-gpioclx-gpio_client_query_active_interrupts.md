---
UID: NC:gpioclx.GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS
title: GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS
author: windows-driver-content
description: The CLIENT_QueryActiveInterrupts event callback function queries the state of a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_queryactiveinterrupts.htm
old-project: GPIO
ms.assetid: 9B47A7B2-90C3-480F-85D8-44DD7E9F0BFA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_queryactiveinterrupts, CLIENT_QueryActiveInterrupts callback function [Parallel Ports], CLIENT_QueryActiveInterrupts, GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS, GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS, gpioclx/CLIENT_QueryActiveInterrupts
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_QueryActiveInterrupts
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---


# GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS callback function
The <i>CLIENT_QueryActiveInterrupts</i> event callback function queries the state of a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.

## Syntax

```
GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS GpioClientQueryActiveInterrupts;

NTSTATUS GpioClientQueryActiveInterrupts(
  PVOID Context,
  PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS QueryActiveParameters
)
{...}
```

## Parameters

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`QueryActiveParameters`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698253">GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</a> structure that, on entry, describes the GPIO interrupt pins to query, and, on exit, contains the active and enabled interrupt state of these pins.


## Return Value

The <i>CLIENT_QueryActiveInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to query a set of GPIO pins that are configured as interrupt request inputs.

The <i>QueryActiveParameters</i> parameter points to a caller-allocated <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. The caller sets the values of the <b>BankId</b> and <b>EnabledMask</b> members of this structure. The <i>CLIENT_QueryActiveInterrupts</i> function writes to the <b>ActiveMask</b> member of the structure.

On entry, the bits that are set in the <b>EnabledMask</b> member should match the set of currently enabled interrupts in the bank. On return, the bits that are set in the <b>ActiveMask</b> member should correspond to interrupts that are both enabled and active. Thus, if a bit in <b>EnabledMask</b> is zero, the corresponding bit in <b>ActiveMask</b> must be zero.

To register your driver's <i>CLIENT_QueryActiveInterrupts</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure that contains a <i>CLIENT_QueryActiveInterrupts</i> function pointer.

GpioClx calls the <i>CLIENT_QueryActiveInterrupts</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_QueryActiveInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | gpioclx.h |
| **IRQL** | See Remarks. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698253">GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_QueryActiveInterrupts callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>