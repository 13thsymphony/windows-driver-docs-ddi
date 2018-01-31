---
UID : NF:wdm.IoWMISetNotificationCallback
title : IoWMISetNotificationCallback function
author : windows-driver-content
description : The IoWMISetNotificationCallback routine registers a notification callback for a WMI event.
old-location : kernel\iowmisetnotificationcallback.htm
old-project : kernel
ms.assetid : c1bd12e0-0862-4e51-a9e8-71eb7b2549fd
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k104_8ee391bd-0abe-4901-b0dc-6266d0c8f5c4.xml, kernel.iowmisetnotificationcallback, IoWMISetNotificationCallback, IoWMISetNotificationCallback routine [Kernel-Mode Driver Architecture], wdm/IoWMISetNotificationCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoWMISetNotificationCallback function
The <b>IoWMISetNotificationCallback</b> routine registers a notification callback for a WMI event.

## Syntax

````
NTSTATUS IoWMISetNotificationCallback(
  _Inout_  PVOID                     Object,
  _In_     WMI_NOTIFICATION_CALLBACK Callback,
  _In_opt_ PVOID                     Context
);
````

## Parameters

`Object`

Pointer to a WMI data block object. The caller opens the data block object for the WMI event with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_NOTIFICATION access right.

`Callback`

Pointer to a function of the form:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> XxxWmiNotificationCallback(PVOID Wnode, PVOID Context);</pre>
</td>
</tr>
</table></span></div>WMI calls this function to notify the caller that the specified event has occurred. The <i>Wnode</i> parameter of the callback routine points to the <a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a> structure returned by the driver triggering the event. The <i>Context</i> parameter of the callback routine points to the value specified in the <i>Context</i> parameter of the <b>IoWMISetNotificationCallback</b> routine.

`Context`

Specifies the value that WMI passes to the callback routine when the event occurs.


## Return Value

This routine returns STATUS_SUCCESS on success, and the appropriate NTSTATUS error code on failure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>

<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMISetNotificationCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>