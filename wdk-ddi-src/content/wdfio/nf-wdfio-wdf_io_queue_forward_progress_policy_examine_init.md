---
UID: NF:wdfio.WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT
title: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function
author: windows-driver-content
description: The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure.
old-location: wdf\wdf_io_queue_forward_progress_policy_examine_init.htm
old-project: wdf
ms.assetid: 3d1d7242-ff26-47e0-a1f6-ae67b27acf22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_bd2ff7de-f07f-4557-9051-d22f23a0530c.xml, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function, kmdf.wdf_io_queue_forward_progress_policy_examine_init, wdf.wdf_io_queue_forward_progress_policy_examine_init, wdfio/WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
-	wdfio.h
api_name:
-	WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---


# WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

## Syntax

```
void WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT(
  PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY   Policy,
  ULONG                                   TotalForwardProgressRequests,
  PFN_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS EvtIoWdmIrpForForwardProgress
);
```

## Parameters

`Policy`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

`TotalForwardProgressRequests`

The number of request objects that the framework will attempt to reserve for use in low-memory situations. This number must be greater than zero.

`EvtIoWdmIrpForForwardProgress`

A pointer to the driver's <a href="https://msdn.microsoft.com/71974802-954d-4856-a32b-1dcc45c36ba5">EvtIoWdmIrpForForwardProgress</a> callback function.


## Return Value

None.

## Remarks

The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and sets its <b>Size</b> member. It also sets the structure's <b>TotalForwardProgressRequests </b>and<b>ForwardProgressReservePolicySettings.Policy.ExaminePolicy.EvtIoWdmIrpForForwardProgress </b>members to the specified values, and it sets the <b>ForwardProgressReservedPolicy</b> member to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547395">WdfIoQueueAssignForwardProgressPolicy</a>. In the example, the driver is specifying that the framework should allocate and reserve 10 request objects for low-memory situations, and that the framework should call the driver's <b>MyIoForwardExamineIrpForForwardProgress</b> callback function before using one of the reserved request objects.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define MAX_RESERVED_REQUESTS 10

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY queueForwardProgressPolicy;
WDFQUEUE readQueue;
NTSTATUS status = STATUS_SUCCESS;

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT(
    &amp;queueForwardProgressPolicy,
    MAX_RESERVED_REQUESTS,
    MyIoForwardExamineIrpForForwardProgress
    );
status = WdfIoQueueAssignForwardProgressPolicy(
    readQueue,
    &amp;queueForwardProgressPolicy
    );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfio.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552365">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552367">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547395">WdfIoQueueAssignForwardProgressPolicy</a>