---
UID: NE:wudfwdm._KINTERRUPT_MODE
title: "_KINTERRUPT_MODE"
author: windows-driver-content
description: The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered.
old-location: kernel\kinterrupt_mode.htm
old-project: kernel
ms.assetid: 2f00fe3f-d73d-4f0f-a1dd-ae72fa57e55d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KINTERRUPT_MODE, KINTERRUPT_MODE enumeration [Kernel-Mode Driver Architecture], Latched, LevelSensitive, _KINTERRUPT_MODE, kernel.kinterrupt_mode, sysenum_35275927-b863-496a-8193-579f9d1d3a22.xml, wdm/KINTERRUPT_MODE, wdm/Latched, wdm/LevelSensitive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	KINTERRUPT_MODE
product: Windows
targetos: Windows
req.typenames: KINTERRUPT_MODE
req.product: Windows 10 or later.
---

# _KINTERRUPT_MODE Enumeration
The <b>KINTERRUPT_MODE</b> enumeration type indicates whether an interrupt is level-triggered or edge-triggered.

## Syntax
````
typedef enum _KINTERRUPT_MODE { 
  LevelSensitive  = 0,
  Latched         = 1
} KINTERRUPT_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>Latched</td>
                    <td>The interrupt is edge-triggered. This is the mode for PCI message-signaled interrupts.</td>
                </tr>
            
                <tr>
                    <td>LevelSensitive</td>
                    <td>The interrupt is level-triggered. This is the mode for traditional PCI line-based interrupts.</td>
                </tr>
</table>

## Remarks

The interrupt mode is an electrical characteristic of the interrupt. A device signals a level-triggered interrupt by changing the voltage on the interrupt pin, and holding it there until the processor signals that the interrupt is received. In contrast, to signal an edge-triggered interrupt, the device changes the voltage state for a fixed period of time, before reverting to the original voltage state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h) |

## See Also

<a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>



<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>



<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KINTERRUPT_MODE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>