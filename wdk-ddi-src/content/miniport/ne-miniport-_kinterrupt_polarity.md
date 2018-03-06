---
UID: NE:miniport._KINTERRUPT_POLARITY
title: "_KINTERRUPT_POLARITY"
author: windows-driver-content
description: The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line.
old-location: kernel\kinterrupt_polarity.htm
old-project: kernel
ms.assetid: 2fcc4597-b169-43a8-b2bb-dd2dd66f29dc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PKINTERRUPT_POLARITY, InterruptActiveBoth, InterruptActiveBothTriggerHigh, InterruptActiveBothTriggerLow, InterruptActiveHigh, InterruptActiveLow, InterruptFallingEdge, InterruptPolarityUnknown, InterruptRisingEdge, KINTERRUPT_POLARITY, KINTERRUPT_POLARITY enumeration [Kernel-Mode Driver Architecture], PKINTERRUPT_POLARITY, PKINTERRUPT_POLARITY enumeration pointer [Kernel-Mode Driver Architecture], _KINTERRUPT_POLARITY, kernel.kinterrupt_polarity, sysenum_56e5681d-ea77-4385-bd47-4add306a4fe8.xml, wdm/InterruptActiveBoth, wdm/InterruptActiveBothTriggerHigh, wdm/InterruptActiveBothTriggerLow, wdm/InterruptActiveHigh, wdm/InterruptActiveLow, wdm/InterruptFallingEdge, wdm/InterruptPolarityUnknown, wdm/InterruptRisingEdge, wdm/KINTERRUPT_POLARITY, wdm/PKINTERRUPT_POLARITY"
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
-	Wdm.h
api_name:
-	KINTERRUPT_POLARITY
product: Windows
targetos: Windows
req.typenames: KINTERRUPT_POLARITY, *PKINTERRUPT_POLARITY
---

# _KINTERRUPT_POLARITY Enumeration
The <b>KINTERRUPT_POLARITY</b> enumeration indicates how a device signals an interrupt request on an interrupt line.

## Syntax
````
typedef enum _KINTERRUPT_POLARITY { 
  InterruptPolarityUnknown,
  InterruptActiveHigh,
  InterruptRisingEdge             = InterruptActiveHigh,
  InterruptActiveLow,
  InterruptFallingEdge            = InterruptActiveLow,
  InterruptActiveBoth,
  InterruptActiveBothTriggerLow   = InterruptActiveBoth,
  InterruptActiveBothTriggerHigh
} KINTERRUPT_POLARITY, *PKINTERRUPT_POLARITY;
````

## Constants

<table>
            
                <tr>
                    <td>InterruptActiveBoth</td>
                    <td>Active-both interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a low-to-high or a high-to-low transition on the interrupt line. After a low-to-high transition signals an interrupt request, the interrupt line remains high until a high-to-low transition signals the next interrupt request. Similarly, after a high-to-low transition signals an interrupt request, the interrupt line remains low until a low-to-high transition signals the next interrupt request.</td>
                </tr>
            
                <tr>
                    <td>InterruptActiveBothTriggerHigh</td>
                    <td>Reserved for use by the operating system.</td>
                </tr>
            
                <tr>
                    <td>InterruptActiveBothTriggerLow</td>
                    <td>Reserved for use by the operating system.</td>
                </tr>
            
                <tr>
                    <td>InterruptActiveHigh</td>
                    <td>Active-high interrupt. The interrupt input type is level-triggered, and an interrupt request is indicated by a high signal level on the interrupt line. The request remains active as long as the line remains high.</td>
                </tr>
            
                <tr>
                    <td>InterruptActiveLow</td>
                    <td>Active-low interrupt. The interrupt input type is level-triggered, and an interrupt request is indicated by a low signal level on the interrupt line. The request remains active as long as the line remains low.</td>
                </tr>
            
                <tr>
                    <td>InterruptFallingEdge</td>
                    <td>Falling-edge-triggered interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a high-to-low transition on the interrupt line.</td>
                </tr>
            
                <tr>
                    <td>InterruptPolarityUnknown</td>
                    <td>The interrupt polarity is unknown.</td>
                </tr>
            
                <tr>
                    <td>InterruptRisingEdge</td>
                    <td>Rising-edge-triggered interrupt. The interrupt input type is edge-triggered, and an interrupt request is indicated by a low-to-high transition on the interrupt line.</td>
                </tr>
</table>

## Remarks

A <b>KINTERRUPT_POLARITY</b> enumeration constant is frequently used in conjunction with a <a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration constant to describe an interrupt signal. A <b>KINTERRUPT_MODE</b> enumeration constant indicates whether the interrupt signal from a device is level-triggered or edge-triggered.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |

## See Also

<a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KINTERRUPT_POLARITY enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>