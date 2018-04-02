---
UID: NE:miniport._IRQ_PRIORITY
title: "_IRQ_PRIORITY"
author: windows-driver-content
description: The IRQ_PRIORITY enumeration type indicates the priority the system should give to servicing a device's interrupts.
old-location: kernel\irq_priority.htm
old-project: kernel
ms.assetid: 1dee65e7-27fb-4665-82e2-d7cb3c223f87
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PIRQ_PRIORITY, IRQ_PRIORITY, IRQ_PRIORITY enumeration [Kernel-Mode Driver Architecture], IrqPriorityHigh, IrqPriorityLow, IrqPriorityNormal, IrqPriorityUndefined, PIRQ_PRIORITY, PIRQ_PRIORITY enumeration pointer [Kernel-Mode Driver Architecture], _IRQ_PRIORITY, kernel.irq_priority, sysenum_a5a51a77-ee9c-4e74-9ee4-b097eb361c18.xml, wdm/IRQ_PRIORITY, wdm/IrqPriorityHigh, wdm/IrqPriorityLow, wdm/IrqPriorityNormal, wdm/IrqPriorityUndefined, wdm/PIRQ_PRIORITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: miniport.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IRQ_PRIORITY
product:
- Windows
targetos: Windows
req.typenames: IRQ_PRIORITY, *PIRQ_PRIORITY
---

# _IRQ_PRIORITY Enumeration
The <b>IRQ_PRIORITY</b> enumeration type indicates the priority the system should give to servicing a device's interrupts.

## Syntax
```
typedef enum _IRQ_PRIORITY {
  IrqPriorityUndefined  ,
  IrqPriorityLow        ,
  IrqPriorityNormal     ,
  IrqPriorityHigh
} IRQ_PRIORITY, *PIRQ_PRIORITY;
```

## Constants

<table>
            
                <tr>
                    <td>IrqPriorityUndefined</td>
                    <td>Specifies that the device does not require any particular priority for its interrupts.</td>
                </tr>
            
                <tr>
                    <td>IrqPriorityLow</td>
                    <td>Specifies that the device's interrupts are of low priority. This setting is appropiate for devices that can tolerate higher-than-normal latency.</td>
                </tr>
            
                <tr>
                    <td>IrqPriorityNormal</td>
                    <td>Specifies that the device's interrupts are of normal priority.</td>
                </tr>
            
                <tr>
                    <td>IrqPriorityHigh</td>
                    <td>Specifies that the device's interrupts are of high priority. This setting is appropriate for devices that require low latency.</td>
                </tr>
</table>

## Remarks

The system uses <b>IRQ_PRIORITY</b> to assign IRQLs for devices. For example, it might assign a higher IRQL to a device that has an <b>IRQ_PRIORITY</b> of <b>IrqPriorityHigh</b> than it does to a device that has an <b>IRQ_PRIORITY</b> of <b>IrqPriorityLow</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>