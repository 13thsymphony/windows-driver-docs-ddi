---
UID : NF:wdftimer.WdfTimerStart
title : WdfTimerStart function
author : windows-driver-content
description : The WdfTimerStart method starts a timer's clock.
old-location : wdf\wdftimerstart.htm
old-project : wdf
ms.assetid : 32c40be2-dee0-4ac7-9f78-a64b9f985f51
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfTimerStart
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
req.alt-api : WdfTimerStart
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product : Windows 10 or later.
---


# WdfTimerStart function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerStart</b> method starts a timer's clock.

## Syntax

````
BOOLEAN WdfTimerStart(
  _In_ WDFTIMER Timer,
  _In_ LONGLONG DueTime
);
````

## Parameters

`Timer`

A handle to a framework timer object that was obtained by calling <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.

`DueTime`

A time period, in system time units (100-nanosecond intervals). The framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function when the specified time period elapses. The time period value can be negative or positive as follows:
<ul>
<li>
If the value is negative, the time period is relative to the current system time.

</li>
<li>If the value is positive, the time period specifies an absolute time (which is actually relative to January 1, 1601).</li>
</ul>


<div class="alert"><b>Warning</b>  If you set the <b>UseHighResolutionTimer</b> member of <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> to <b>WdfTrue</b>, you must call <b>WdfTimerStart</b> with the <i>DueTime</i> parameter set to a negative value.  Otherwise, the call causes the system to crash.</div>
<div> </div>
Relative times are not affected by any changes to the system time that might occur within the specified time period. Absolute times do reflect system time changes.

The framework provides <a href="https://msdn.microsoft.com/E7D5564D-7BAA-412E-959F-3655B963B4C1">time conversion functions</a> that convert time values into system time units.


## Return Value

<b>WdfTimerStart</b> returns <b>TRUE</b> if the timer object was in the system's timer queue. Otherwise, this method returns <b>FALSE</b>. For more information, see the following Remarks section. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

After a driver calls <b>WdfTimerStart</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function when the time that is specified for the <i>DueTime</i> parameter elapses. After this first call, the framework calls the callback function each time that the time period that is specified by the <b>Period</b> member of the driver's <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure elapses. 

The expiration of the timer ultimately depends on the granularity of the system clock. The value specified for <i>DueTime</i> guarantees that the framework calls the driver's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function on or after the given <i>DueTime</i>. However, <b>WdfTimerStart</b> cannot override the granularity of the system clock, whatever the value specified for <i>DueTime</i>. 

When a driver calls <b>WdfTimerStart</b>, its timer object is added to the system's queue of timer objects. If the timer is not a periodic timer, the system removes the timer object from the queue after the timer's "due time" has elapsed. If the timer is a periodic timer, the timer object remains in the queue until the driver calls <a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>.

A driver might call <b>WdfTimerStart</b> from its <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function in order to restart a non-periodic timer after it expires.

<b>WdfTimerStart</b> returns <b>TRUE</b> if the driver has previously called <b>WdfTimerStart</b> and the timer object is still in the system's queue because the time period has not elapsed (or because it is a periodic timer). Before <b>WdfTimerStart</b> returns <b>TRUE</b>, the operating system resets the time period to the value that the driver specified in the new call to <b>WdfTimerStart</b>. The framework calls the <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function only after the new time period elapses.

To stop the timer's clock, the driver can call <a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.

The following code example starts a timer. The framework will call the timer's <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback function after 10 milliseconds.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdftimer.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a>
</dt>
<dt>
<a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>
</dt>
<dt>
<a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>
</dt>
<dt>
<a href="..\wdftimer\nf-wdftimer-wdftimerstop.md">WdfTimerStop</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfTimerStart method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>