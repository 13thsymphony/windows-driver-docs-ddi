---
UID : NE:d3dkmddi._DXGK_INTERRUPT_TYPE
title : "_DXGK_INTERRUPT_TYPE"
author : windows-driver-content
description : The DXGK_INTERRUPT_TYPE enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about.
old-location : display\dxgk_interrupt_type.htm
old-project : display
ms.assetid : f942e448-94b8-400b-927b-fb5f2b1f544e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, d3dkmddi/DXGK_INTERRUPT_TYPE, DXGK_INTERRUPT_TYPE, DXGK_INTERRUPT_DMA_FAULTED, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, DXGK_INTERRUPT_TYPE enumeration [Display Devices], d3dkmddi/DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, d3dkmddi/DXGK_INTERRUPT_DMA_PREEMPTED, DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, d3dkmddi/DXGK_INTERRUPT_DMA_COMPLETED, d3dkmddi/DXGK_INTERRUPT_DMA_FAULTED, DmEnums_5ed0a892-5813-43ff-aae9-25b03aa3ea5f.xml, DXGK_INTERRUPT_DMA_COMPLETED, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_VSYNC, d3dkmddi/DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, DXGK_INTERRUPT_DMA_PREEMPTED, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, DXGK_INTERRUPT_DMA_PAGE_FAULTED, display.dxgk_interrupt_type, DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC, d3dkmddi/DXGK_INTERRUPT_DMA_PAGE_FAULTED, _DXGK_INTERRUPT_TYPE, DXGK_INTERRUPT_CRTC_VSYNC, DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, DXGK_INTERRUPT_DISPLAYONLY_VSYNC
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_INTERRUPT_TYPE
---

# _DXGK_INTERRUPT_TYPE Enumeration
The DXGK_INTERRUPT_TYPE enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about.

## Syntax
````
typedef enum _DXGK_INTERRUPT_TYPE { 
  DXGK_INTERRUPT_DMA_COMPLETED                       = 1,
  DXGK_INTERRUPT_DMA_PREEMPTED                       = 2,
  DXGK_INTERRUPT_CRTC_VSYNC                          = 3,
  DXGK_INTERRUPT_DMA_FAULTED                         = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGK_INTERRUPT_DISPLAYONLY_VSYNC                   = 5,
  DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS        = 6,
  DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY  = 7,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
  DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE      = 8,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  DXGK_INTERRUPT_DMA_PAGE_FAULTED                    = 9,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
  DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED   = 11
} DXGK_INTERRUPT_TYPE;
````

## Constants

<table>

<tr>
<td>DXGK_INTERRUPT_CRTC_VSYNC</td>
<td>A scan out is completed. The driver must supply information in the <b>CrtcVsync</b> structure in the union that is contained in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function. 

The display miniport driver notifies with this interrupt type after video hardware entered into the vertical retrace period, and the pending flip address was latched into the DAC and scanned out. The display miniport driver is not required to report this interrupt after the operating system calls the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a> function to disable the interrupt type; however, the driver must resume reporting after the operating system calls the driver's <i>DxgkDdiControlInterrupt</i> function again to enable the interrupt type.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY</td>
<td>A Vsync has completed in a display miniport driver that supports multiplane overlays.

Supported starting with Windows 8.1.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY2</td>
<td></td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS</td>
<td>In a kernel mode display-only driver, a present operation has completed or has failed.

Supported starting with Windows 8.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DISPLAYONLY_VSYNC</td>
<td>In a kernel mode display-only driver, a VSync has completed.

Supported starting with Windows 8.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DMA_COMPLETED</td>
<td>A direct memory access (DMA) buffer is completed by using a fence identifier. The driver must supply the DMA buffer fence identifier in the <b>SubmissionFenceId</b> member of the <b>DmaCompleted</b> structure in the union that is contained in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function. This DMA buffer fence identifier was assigned during a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function for the latest completed DMA buffer.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DMA_FAULTED</td>
<td>Reserved for system use. Do not use in your driver.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DMA_PAGE_FAULTED</td>
<td>This interrupt type should be raised when a GPU encounters an error condition that requires OS to perform a recovery action, such as putting the running packet device in error or resetting the GPU.


When this interrupt type is set, interrupt data should be provided in the <b>DmaPageFaulted</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure.

Supported starting with Windows 10.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_DMA_PREEMPTED</td>
<td>A preemption request is completed. The driver must supply the preemption fence identifier in the <b>PreemptionFenceId</b> member and the latest fence identifier that hardware completed (not preempted) in the <b>LastCompletedFenceId</b> member of the <b>DmaPreempted</b> structure in the union that is contained in the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.

The GPU scheduler determines that the graphics hardware preempted all of the commands between the preemption request and the submission with the latest fence identifier.</td>
</tr>

<tr>
<td>DXGK_INTERRUPT_HWCONTEXTLIST_SWITCH_COMPLETED</td>
<td></td>
</tr>

<tr>
<td>DXGK_INTERRUPT_HWQUEUE_PAGE_FAULTED</td>
<td></td>
</tr>

<tr>
<td>DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE</td>
<td></td>
</tr>

<tr>
<td>DXGK_INTERRUPT_MONITORED_FENCE_SIGNALED</td>
<td></td>
</tr>

<tr>
<td>DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED</td>
<td>This interrupt type should be raised when the periodic monitored fence is signaled. 

Supported starting with Windows 10.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a>

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_INTERRUPT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>