---
UID : NF:wdftimer.WDF_TIMER_CONFIG_INIT
title : WDF_TIMER_CONFIG_INIT function
author : windows-driver-content
description : The WDF_TIMER_CONFIG_INIT function initializes a WDF_TIMER_CONFIG structure for a timer that will use a single due time.
old-location : wdf\wdf_timer_config_init.htm
old-project : wdf
ms.assetid : 2bf613ff-e178-4a33-a1ae-ea6d4bb78d0a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WDF_TIMER_CONFIG_INIT, wdftimer/WDF_TIMER_CONFIG_INIT, kmdf.wdf_timer_config_init, DFTimerObjectRef_aed045cc-b5e1-4e47-8f6b-41d6b858c9f2.xml, wdf.wdf_timer_config_init, WDF_TIMER_CONFIG_INIT function
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdftimer.h
req.include-header : Wdf.h
req.target-type : Universal
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
req.lib : None
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product : Windows 10 or later.
---


# WDF_TIMER_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_TIMER_CONFIG_INIT</b> function initializes a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure for a timer that will use a single due time.

## Syntax

````
VOID WDF_TIMER_CONFIG_INIT(
  _In_ PWDF_TIMER_CONFIG Config,
  _In_ PFN_WDF_TIMER     EvtTimerFunc
);
````

## Parameters

`Config`

A pointer to a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure.

`EvtTimerFunc`

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function.


## Return Value

None

## Remarks

The <b>WDF_TIMER_CONFIG_INIT</b> function zeros the specified <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure. Then it sets the structure's <b>Size</b> member, stores the <i>EvtTimerFunc</i> pointer, sets the <b>Period</b> member and the <b>TolerableDelay</b> member to zero, and sets the <b>AutomaticSerialization</b> member to <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdftimer.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdftimer\nf-wdftimer-wdf_timer_config_init_periodic.md">WDF_TIMER_CONFIG_INIT_PERIODIC</a>

<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>

<a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_TIMER_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>