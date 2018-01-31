---
UID : NE:wdfinterrupt._WDF_INTERRUPT_POLARITY
title : "_WDF_INTERRUPT_POLARITY"
author : windows-driver-content
description : The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity.
old-location : wdf\wdf_interrupt_polarity.htm
old-project : wdf
ms.assetid : 6621a1ec-1d4e-4801-9418-d09a0073686a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfinterrupt/WdfInterruptPolarityUnknown, PWDF_INTERRUPT_POLARITY, DFInterruptObjectRef_979c7766-edd8-421b-8885-8000d60da78d.xml, wdfinterrupt/WDF_INTERRUPT_POLARITY, WdfInterruptPolarityUnknown, _WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY, wdfinterrupt/PWDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY enumeration, kmdf.wdf_interrupt_polarity, wdfinterrupt/WdfInterruptActiveLow, wdf.wdf_interrupt_polarity, WdfInterruptActiveHigh, WdfInterruptActiveLow, wdfinterrupt/WdfInterruptActiveHigh, PWDF_INTERRUPT_POLARITY enumeration pointer
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfinterrupt.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY
req.product : Windows 10 or later.
---

# _WDF_INTERRUPT_POLARITY Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify an interrupt signal's polarity.

## Syntax
````
typedef enum _WDF_INTERRUPT_POLARITY { 
  WdfInterruptPolarityUnknown  = 0,
  WdfInterruptActiveHigh       = 1,
  WdfInterruptActiveLow        = 2
} WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY;
````

## Constants

<table>

<tr>
<td>WdfInterruptActiveHigh</td>
<td>The interrupt signal is active when it is high.</td>
</tr>

<tr>
<td>WdfInterruptActiveLow</td>
<td>The interrupt signal is active when it is low.</td>
</tr>

<tr>
<td>WdfInterruptPolarityUnknown</td>
<td>The interrupt signal's polarity is unknown.</td>
</tr>
</table>

## Remarks

The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify a member of the <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |

## See Also

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_POLARITY enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>