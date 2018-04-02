---
UID: NE:wdfinterrupt._WDF_INTERRUPT_POLARITY
title: "_WDF_INTERRUPT_POLARITY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity.
old-location: wdf\wdf_interrupt_polarity.htm
old-project: wdf
ms.assetid: 6621a1ec-1d4e-4801-9418-d09a0073686a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_POLARITY, DFInterruptObjectRef_979c7766-edd8-421b-8885-8000d60da78d.xml, PWDF_INTERRUPT_POLARITY, PWDF_INTERRUPT_POLARITY enumeration pointer, WDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY enumeration, WdfInterruptActiveHigh, WdfInterruptActiveLow, WdfInterruptPolarityUnknown, _WDF_INTERRUPT_POLARITY, kmdf.wdf_interrupt_polarity, wdf.wdf_interrupt_polarity, wdfinterrupt/PWDF_INTERRUPT_POLARITY, wdfinterrupt/WDF_INTERRUPT_POLARITY, wdfinterrupt/WdfInterruptActiveHigh, wdfinterrupt/WdfInterruptActiveLow, wdfinterrupt/WdfInterruptPolarityUnknown"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfinterrupt.h
api_name:
-	WDF_INTERRUPT_POLARITY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_POLARITY Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify an interrupt signal's polarity.

## Syntax
```
typedef enum _WDF_INTERRUPT_POLARITY {
  WdfInterruptPolarityUnknown  ,
  WdfInterruptActiveHigh       ,
  WdfInterruptActiveLow
} *PWDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY;
```

## Constants

<table>
            
                <tr>
                    <td>WdfInterruptPolarityUnknown</td>
                    <td>The interrupt signal's polarity is unknown.</td>
                </tr>
            
                <tr>
                    <td>WdfInterruptActiveHigh</td>
                    <td>The interrupt signal is active when it is high.</td>
                </tr>
            
                <tr>
                    <td>WdfInterruptActiveLow</td>
                    <td>The interrupt signal is active when it is low.</td>
                </tr>
</table>

## Remarks

The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a>