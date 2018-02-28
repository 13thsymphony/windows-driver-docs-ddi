---
UID: NC:dispmprt.DXGKCB_INDICATE_CHILD_STATUS
title: DXGKCB_INDICATE_CHILD_STATUS
author: windows-driver-content
description: The DxgkCbIndicateChildStatus function records the current status of a specified child device of a display adapter.
old-location: display\dxgkcbindicatechildstatus.htm
old-project: display
ms.assetid: 780a8867-bba1-4b1b-a941-b55bfe087b7b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKCB_INDICATE_CHILD_STATUS, DpFunctions_db80be21-a515-411f-beb0-64f7514c11f4.xml, DxgkCbIndicateChildStatus, DxgkCbIndicateChildStatus callback function [Display Devices], display.dxgkcbindicatechildstatus, dispmprt/DxgkCbIndicateChildStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbIndicateChildStatus
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKCB_INDICATE_CHILD_STATUS callback function
The <b>DxgkCbIndicateChildStatus</b> function records the current status of a specified child device of a display adapter.

## Syntax

```
DXGKCB_INDICATE_CHILD_STATUS DxgkcbIndicateChildStatus;

NTSTATUS DxgkcbIndicateChildStatus(
  HANDLE DeviceHandle,
  PDXGK_CHILD_STATUS ChildStatus
)
{...}
```

## Parameters

`DeviceHandle`

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.

`ChildStatus`

A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_status.md">DXGK_CHILD_STATUS</a> structure that identifies the child device and describes the current status of the child device.


## Return Value

<b>DxgkCbIndicateChildStatus</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

The display miniport driver's DPC for ISR calls <b>DxgkCbIndicateChildStatus</b> when the display adapter generates an interrupt for any of the following reasons:

<ul>
<li>
An external device (typically a monitor) has been connected to one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.

</li>
<li>
An external device (typically a monitor) has been disconnected from one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.

</li>
<li>
The display device connected to one of its on-board child devices (that has a monitor orientation awareness value of <b>D3DKMDT_MOA_INTERRUPTIBLE</b>) has been rotated. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusRotation</b> and sets<i> ChildStatus</i>.<b>Rotation</b>.<b>Angle</b> to the angle of rotation.

</li>
</ul>
The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a> function calls <b>DxgkCbIndicateChildStatus</b> in the following situations:

<ul>
<li>
The lid on a portable computer gets opened. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.

</li>
<li>
The lid on a portable computer gets closed. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.

</li>
</ul>

#### Examples

The following code example shows how to record the current status of a child device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
AtiSimulateMonitor(HW_DEVICE_EXTENSION *pHwDeviceExtension, PR2_SIMULATE_MONITOR i_pEscape)
{
    NTSTATUS Status;
    PVOID MonitorDescriptor = NULL;
    DXGK_CHILD_STATUS     ChildStatus;
    ChildStatus.ChildUid    =  pHwDeviceExtension-&gt;ulNumberDisplays | HW_ID_DISPLAY_CHILD;
    ChildStatus.Type    = StatusConnection;

    if(i_pEscape-&gt;Data == NULL) {
        // Remove a simulated monitor
        if(pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor != NULL) {
            ExFreePoolWithTag(pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor, ATI_TAG);
            pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor = NULL;
            pHwDeviceExtension-&gt;ulSimulatedMonitorDescriptorLength = 0;
           pHwDeviceExtension-&gt;ulRetryCount = 0;
           pHwDeviceExtension-&gt;bReportDescriptor = FALSE;

            ChildStatus.HotPlug.Connected = FALSE;
            Status = DxgkCbIndicateChildStatus(pHwDeviceExtension-&gt;DeviceHandle, &amp;ChildStatus);
        }
        else {
            // No simulated monitor is present so the request to remove one is invalid
            return STATUS_INVALID_PARAMETER;
        }
    }
    else {
        //Add a simulated monitor
    }
    return Status;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_INDICATE_CHILD_STATUS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>