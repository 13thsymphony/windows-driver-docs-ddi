---
UID : NC:gpioclx.GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT
title : GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT
author : windows-driver-content
description : The CLIENT_RestoreBankHardwareContext event callback function restores the hardware context of a bank of general-purpose I/O (GPIO) pins.
old-location : gpio\client_restorebankhardwarecontext.htm
old-project : GPIO
ms.assetid : 7F73BC89-1BAF-413D-A901-56B4A0F3235A
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GPIO.client_restorebankhardwarecontext, CLIENT_RestoreBankHardwareContext callback function [Parallel Ports], CLIENT_RestoreBankHardwareContext, GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT, GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT, gpioclx/CLIENT_RestoreBankHardwareContext
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


# GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT callback function
The <i>CLIENT_RestoreBankHardwareContext</i> event callback function restores the hardware context of a bank of general-purpose I/O (GPIO) pins.

## Syntax

```
GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT GpioClientRestoreBankHardwareContext;

void GpioClientRestoreBankHardwareContext(
  PVOID Context,
  PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS Parameters
)
{...}
```

## Parameters

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`Parameters`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698257">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a> structure that describes the bank of GPIO pins to restore.


## Return Value

The <i>CLIENT_RestoreBankHardwareContext</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## Remarks

If a bank of GPIO pins supports component-level power management, GpioClx can switch the bank to a low-power Fx state if the bank is idle. If the GPIO controller bank loses its hardware context in the Fx state, the GPIO controller driver must save this context before the F0-to-Fx transition, and, later, restore the context after the Fx-to-F0 transition. Currently, F1 is the only low-power state that is defined for GPIO controllers that use GpioClx.

GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> function to restore the bank's previously saved hardware context. The hardware context was previously saved by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a> event callback function.

Some GPIO controller devices enable selected banks of pins to be turned on and off independently of other banks in the same device. Thus, power can be saved by turning off a bank that is idle.

To register your driver's <i>CLIENT_RestoreBankHardwareContext</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_RestoreBankHardwareContext</i> function pointer.

GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698257">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_RestoreBankHardwareContext callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>