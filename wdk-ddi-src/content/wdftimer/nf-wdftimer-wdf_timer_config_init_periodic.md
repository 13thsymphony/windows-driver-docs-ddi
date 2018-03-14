---
UID: NF:wdftimer.WDF_TIMER_CONFIG_INIT_PERIODIC
title: WDF_TIMER_CONFIG_INIT_PERIODIC function
author: windows-driver-content
description: The WDF_TIMER_CONFIG_INIT_PERIODIC function initializes a WDF_TIMER_CONFIG structure for a periodic timer.
old-location: wdf\wdf_timer_config_init_periodic.htm
old-project: wdf
ms.assetid: 44a5b4dd-c654-4af1-afd6-6e59d2cd1ff8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFTimerObjectRef_de3c1624-3004-46e3-b6b4-d47768cd8239.xml, WDF_TIMER_CONFIG_INIT_PERIODIC, WDF_TIMER_CONFIG_INIT_PERIODIC function, kmdf.wdf_timer_config_init_periodic, wdf.wdf_timer_config_init_periodic, wdftimer/WDF_TIMER_CONFIG_INIT_PERIODIC
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
-	WDF_TIMER_CONFIG_INIT_PERIODIC
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WDF_TIMER_CONFIG_INIT_PERIODIC function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_TIMER_CONFIG_INIT_PERIODIC</b> function initializes a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure for a periodic timer.

## Syntax

````
VOID WDF_TIMER_CONFIG_INIT_PERIODIC(
  _In_ PWDF_TIMER_CONFIG Config,
  _In_ PFN_WDF_TIMER     EvtTimerFunc,
  _In_ LONG              Period
);
````

## Parameters

`Config`

A pointer to a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure.

`EvtTimerFunc`

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function.

`Period`

A time value. For more information about specifying this value, see <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>.


## Return Value

None

## Remarks

The <b>WDF_TIMER_CONFIG_INIT_PERIODIC</b> function zeros the specified <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure. Then it sets the structure's <b>Size</b> member, stores the <i>EvtTimerFunc</i> pointer and <i>Period</i> value, sets the <b>TolerableDelay</b> member to zero and sets the <b>AutomaticSerialization</b> member to <b>TRUE</b>. 


#### Examples

The following code example initializes a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure and a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure and then calls <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_TIMER_CONFIG  timerConfig;
WDF_OBJECT_ATTRIBUTES  timerAttributes;
WDFTIMER  timerHandle;
NTSTATUS  Status;

WDF_TIMER_CONFIG_INIT_PERIODIC(
                               &amp;timerConfig,
                               EchoEvtTimerFunc,
                               PERIODIC_TIMER_INTERVAL
                               );

WDF_OBJECT_ATTRIBUTES_INIT(&amp;timerAttributes);
timerAttributes.ParentObject = Queue;

Status = WdfTimerCreate(
                        &amp;timerConfig,
                        &amp;timerAttributes,
                        &amp;timerHandle
                        );</pre>
</td>
</tr>
</table></span></div>

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

<a href="..\wdftimer\nf-wdftimer-wdf_timer_config_init.md">WDF_TIMER_CONFIG_INIT</a>



<a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>



<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_TIMER_CONFIG_INIT_PERIODIC function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>