---
UID: NE:wdm._IRQ_PRIORITY
title: "_IRQ_PRIORITY"
author: windows-driver-content
description: The IRQ_PRIORITY enumeration type indicates the priority the system should give to servicing a device's interrupts.
old-location: kernel\irq_priority.htm
old-project: kernel
ms.assetid: 1dee65e7-27fb-4665-82e2-d7cb3c223f87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IRQ_PRIORITY, IrqPriorityNormal, _IRQ_PRIORITY, PIRQ_PRIORITY, sysenum_a5a51a77-ee9c-4e74-9ee4-b097eb361c18.xml, PIRQ_PRIORITY enumeration pointer [Kernel-Mode Driver Architecture], wdm/IrqPriorityUndefined, kernel.irq_priority, IrqPriorityLow, wdm/IrqPriorityLow, IRQ_PRIORITY, wdm/IrqPriorityNormal, wdm/IrqPriorityHigh, IRQ_PRIORITY enumeration [Kernel-Mode Driver Architecture], wdm/PIRQ_PRIORITY, *PIRQ_PRIORITY, IrqPriorityUndefined, IrqPriorityHigh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	IRQ_PRIORITY
product: Windows
targetos: Windows
req.typenames: "*PIRQ_PRIORITY, IRQ_PRIORITY"
req.product: Windows 10 or later.
---

# _IRQ_PRIORITY Enumeration
The <b>IRQ_PRIORITY</b> enumeration type indicates the priority the system should give to servicing a device's interrupts.

## Syntax
````
typedef enum _IRQ_PRIORITY { 
  IrqPriorityUndefined  = 0,
  IrqPriorityLow        = 1,
  IrqPriorityNormal     = 2,
  IrqPriorityHigh       = 3
} IRQ_PRIORITY, *PIRQ_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>IrqPriorityHigh</td>
                    <td>Specifies that the device's interrupts are of high priority. This setting is appropriate for devices that require low latency.</td>
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
                    <td>IrqPriorityUndefined</td>
                    <td>Specifies that the device does not require any particular priority for its interrupts.</td>
                </tr>
</table>

## Remarks

The system uses <b>IRQ_PRIORITY</b> to assign IRQLs for devices. For example, it might assign a higher IRQL to a device that has an <b>IRQ_PRIORITY</b> of <b>IrqPriorityHigh</b> than it does to a device that has an <b>IRQ_PRIORITY</b> of <b>IrqPriorityLow</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IRQ_PRIORITY enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>