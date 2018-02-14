---
UID: NE:wdfinterrupt._WDF_INTERRUPT_PRIORITY
title: "_WDF_INTERRUPT_PRIORITY"
author: windows-driver-content
description: The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts.
old-location: wdf\wdf_interrupt_priority.htm
old-project: wdf
ms.assetid: e3305a9c-8107-4631-974b-fe85779ec8dc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: "_WDF_INTERRUPT_PRIORITY, PWDF_INTERRUPT_PRIORITY, PWDF_INTERRUPT_PRIORITY enumeration pointer, wdfinterrupt/WDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY, WdfIrqPriorityNormal, WdfIrqPriorityHigh, wdfinterrupt/WdfIrqPriorityHigh, kmdf.wdf_interrupt_priority, WdfIrqPriorityUndefined, wdfinterrupt/WdfIrqPriorityLow, WdfIrqPriorityLow, *PWDF_INTERRUPT_PRIORITY, wdfinterrupt/WdfIrqPriorityUndefined, wdfinterrupt/PWDF_INTERRUPT_PRIORITY, wdfinterrupt/WdfIrqPriorityNormal, DFInterruptObjectRef_924e187c-58f4-4616-a505-6d1c03779f02.xml, WDF_INTERRUPT_PRIORITY enumeration, wdf.wdf_interrupt_priority"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfinterrupt.h
apiname:
-	WDF_INTERRUPT_PRIORITY
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_PRIORITY Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_PRIORITY</b> enumeration type identifies relative priorities for device interrupts.

## Syntax
````
typedef enum _WDF_INTERRUPT_PRIORITY { 
  WdfIrqPriorityUndefined  = 0,
  WdfIrqPriorityLow        = 1,
  WdfIrqPriorityNormal     = 2,
  WdfIrqPriorityHigh       = 3
} WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIrqPriorityHigh</td>
                    <td>The device's interrupt has a relatively high priority, typically because the interrupt must be serviced immediately.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPriorityLow</td>
                    <td>The device's interrupt has a relatively low priority, typically because the interrupt does not have to be serviced immediately.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPriorityNormal</td>
                    <td>The device's interrupt priority is neither relatively low nor relatively high.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPriorityUndefined</td>
                    <td>The relative priority of a device's interrupt is undefined.</td>
                </tr>
</table>

    ## Remarks

        The <b>WDF_INTERRUPT_PRIORITY</b> enumeration type is used as input to the <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetpolicy.md">WdfInterruptSetPolicy</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |

    ## See Also

        <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetpolicy.md">WdfInterruptSetPolicy</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_PRIORITY enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>