---
UID: NE:wdm._IRQ_DEVICE_POLICY
title: "_IRQ_DEVICE_POLICY"
author: windows-driver-content
description: The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.
old-location: kernel\irq_device_policy.htm
old-project: kernel
ms.assetid: 1a605eed-d9a1-4a2f-a095-3e790061527b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PIRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY enumeration [Kernel-Mode Driver Architecture], IrqPolicyAllCloseProcessors, IrqPolicyAllProcessorsInMachine, IrqPolicyMachineDefault, IrqPolicyOneCloseProcessor, IrqPolicySpecifiedProcessors, IrqPolicySpreadMessagesAcrossAllProcessors, PIRQ_DEVICE_POLICY, PIRQ_DEVICE_POLICY enumeration pointer [Kernel-Mode Driver Architecture], _IRQ_DEVICE_POLICY, kernel.irq_device_policy, sysenum_09bcf230-5558-447e-8646-c60d807365d4.xml, wdm/IRQ_DEVICE_POLICY, wdm/IrqPolicyAllCloseProcessors, wdm/IrqPolicyAllProcessorsInMachine, wdm/IrqPolicyMachineDefault, wdm/IrqPolicyOneCloseProcessor, wdm/IrqPolicySpecifiedProcessors, wdm/IrqPolicySpreadMessagesAcrossAllProcessors, wdm/PIRQ_DEVICE_POLICY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IRQ_DEVICE_POLICY
product:
- Windows
targetos: Windows
req.typenames: IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY
req.product: Windows 10 or later.
---

# _IRQ_DEVICE_POLICY Enumeration
The <b>IRQ_DEVICE_POLICY</b> enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.

## Syntax
```
typedef enum _IRQ_DEVICE_POLICY {
  IrqPolicyMachineDefault                     ,
  IrqPolicyAllCloseProcessors                 ,
  IrqPolicyOneCloseProcessor                  ,
  IrqPolicyAllProcessorsInMachine             ,
  IrqPolicySpecifiedProcessors                ,
  IrqPolicySpreadMessagesAcrossAllProcessors  ,
  IrqPolicyAllProcessorsInMachineWhenSteered
} IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY;
```

## Constants

<table>
            
                <tr>
                    <td>IrqPolicyMachineDefault</td>
                    <td>The device does not require any particular assignment of interrupts to processors.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicyAllCloseProcessors</td>
                    <td>The operating system should assign interrupts from the device to processors that are close to the device. On non-NUMA computers, the effect of this value is identical to that of <b>IrqPolicyAllProcessorsInMachine</b>.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicyOneCloseProcessor</td>
                    <td>The operating system should assign a single interrupt for the device to one processor that is close to the device. On non-NUMA computers, the operating system can assign the interrupt to any processor.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicyAllProcessorsInMachine</td>
                    <td>The operating system should assign interrupts from the device to all processors.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicySpecifiedProcessors</td>
                    <td>The operating system should assign interrupts from the device to a specific set of processors.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicySpreadMessagesAcrossAllProcessors</td>
                    <td>The operating system should assign different message-signaled interrupts to different processors, if possible.</td>
                </tr>
            
                <tr>
                    <td>IrqPolicyAllProcessorsInMachineWhenSteered</td>
                    <td></td>
                </tr>
</table>

## Remarks

The <b>Interrupt.AffinityPolicy</b> member of the <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structure is an <b>IRQ_DEVICE_POLICY</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>