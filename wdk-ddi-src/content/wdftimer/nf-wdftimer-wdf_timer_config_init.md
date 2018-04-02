---
UID: NF:wdftimer.WDF_TIMER_CONFIG_INIT
title: WDF_TIMER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_TIMER_CONFIG_INIT function initializes a WDF_TIMER_CONFIG structure for a timer that will use a single due time.
old-location: wdf\wdf_timer_config_init.htm
old-project: wdf
ms.assetid: 2bf613ff-e178-4a33-a1ae-ea6d4bb78d0a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFTimerObjectRef_aed045cc-b5e1-4e47-8f6b-41d6b858c9f2.xml, WDF_TIMER_CONFIG_INIT, WDF_TIMER_CONFIG_INIT function, kmdf.wdf_timer_config_init, wdf.wdf_timer_config_init, wdftimer/WDF_TIMER_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.lib: None
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	None
-	None.dll
api_name:
-	WDF_TIMER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WDF_TIMER_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_TIMER_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552519">WDF_TIMER_CONFIG</a> structure for a timer that will use a single due time.

## Syntax

```
void WDF_TIMER_CONFIG_INIT(
  PWDF_TIMER_CONFIG Config,
  PFN_WDF_TIMER     EvtTimerFunc
);
```

## Parameters

`Config`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552519">WDF_TIMER_CONFIG</a> structure.

`EvtTimerFunc`

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function.


## Return Value

None

## Remarks

The <b>WDF_TIMER_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552519">WDF_TIMER_CONFIG</a> structure. Then it sets the structure's <b>Size</b> member, stores the <i>EvtTimerFunc</i> pointer, sets the <b>Period</b> member and the <b>TolerableDelay</b> member to zero, and sets the <b>AutomaticSerialization</b> member to <b>TRUE</b>. 


#### Examples

For a code example that uses <b>WDF_TIMER_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550050">WdfTimerCreate</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdftimer.h (include Wdf.h) |
| **Library** | None |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552519">WDF_TIMER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552526">WDF_TIMER_CONFIG_INIT_PERIODIC</a>