---
UID : NF:wdftimer.WdfTimerCreate
title : WdfTimerCreate function
author : windows-driver-content
description : The WdfTimerCreate method creates a framework timer object.
old-location : wdf\wdftimercreate.htm
old-project : wdf
ms.assetid : 577b7629-13ff-4a2d-9f9f-a140d8442bd3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : PFN_WDFTIMERCREATE, wdf.wdftimercreate, WdfTimerCreate method, kmdf.wdftimercreate, wdftimer/WdfTimerCreate, WdfTimerCreate, DFTimerObjectRef_3388a92e-119d-4208-9cf5-2c934435ff25.xml
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
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product : Windows 10 or later.
---


# WdfTimerCreate function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerCreate</b> method creates a framework timer object.

## Syntax

````
NTSTATUS WdfTimerCreate(
  _In_  PWDF_TIMER_CONFIG      Config,
  _In_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_ WDFTIMER               *Timer
);
````

## Parameters

`Config`

A pointer to a <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure.

`Attributes`

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new timer object.

`Timer`

A pointer to a location that receives a handle to the new framework timer object.


## Return Value

<b>WdfTimerCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PARENT_NOT_SPECIFIED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Attributes</i> parameter was <b>NULL</b>, or the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that <i>Attributes</i> specifies was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure did not reference a framework device object or an object whose chain of parents leads to a framework device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member of the <a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a> structure was set to <b>TRUE</b>, but the parent device object's <a href="..\wdfobject\ne-wdfobject-_wdf_execution_level.md">execution level</a> was set to <b>WdfExecutionLevelPassive</b>.

</td>
</tr>
</table> 

For a list of other return values that the <b>WdfTimerCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

When your driver calls <b>WdfTimerCreate</b>, it must supply a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure and must specify a parent object in the structure's <b>ParentObject</b> member. The parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the timer object when it deletes the device object.

After creating a timer object, the driver calls <a href="..\wdftimer\nf-wdftimer-wdftimerstart.md">WdfTimerStart</a> to start the timer's clock. 

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework timer object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdftimer.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdftimer\nf-wdftimer-wdf_timer_config_init.md">WDF_TIMER_CONFIG_INIT</a>

<a href="..\wdftimer\nf-wdftimer-wdftimerstart.md">WdfTimerStart</a>

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>

<a href="..\wdftimer\ns-wdftimer-_wdf_timer_config.md">WDF_TIMER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfTimerCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>