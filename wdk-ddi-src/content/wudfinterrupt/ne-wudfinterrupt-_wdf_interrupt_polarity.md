---
UID: NE:wudfinterrupt._WDF_INTERRUPT_POLARITY
title: "_WDF_INTERRUPT_POLARITY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity.
old-location: wdf\wdf_interrupt_polarity_umdf.htm
old-project: wdf
ms.assetid: 30E61DCE-D88C-47B5-B5CD-3C43C6157FBA
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfinterrupt/WDF_INTERRUPT_POLARITY, wudfinterrupt/WdfInterruptActiveHigh, PWDF_INTERRUPT_POLARITY enumeration pointer, umdf.wdf_interrupt_polarity, WdfInterruptActiveHigh, WDF_INTERRUPT_POLARITY enumeration, WdfInterruptActiveLow, wudfinterrupt/PWDF_INTERRUPT_POLARITY, WdfInterruptPolarityUnknown, wudfinterrupt/WdfInterruptPolarityUnknown, wudfinterrupt/WdfInterruptActiveLow, wdf.wdf_interrupt_polarity_umdf, *PWDF_INTERRUPT_POLARITY, PWDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY, _WDF_INTERRUPT_POLARITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfinterrupt.h
apiname:
-	WDF_INTERRUPT_POLARITY
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_POLARITY Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_polarity.md">WDF_INTERRUPT_POLARITY</a> enumeration type is used to specify an interrupt signal's polarity.

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

        The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_polarity.md">WDF_INTERRUPT_POLARITY</a> enumeration type is used to specify a member of the <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfinterrupt.h |