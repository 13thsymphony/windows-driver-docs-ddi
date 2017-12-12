---
UID: NS.D3DKMDDI._DXGKARG_PREEMPTCOMMAND
title: _DXGKARG_PREEMPTCOMMAND
author: windows-driver-content
description: The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the DxgkDdiSubmitCommand function previously submitted to the hardware command execution unit.
old-location: display\dxgkarg_preemptcommand.htm
old-project: display
ms.assetid: de8f8bee-44e9-4a6a-bb36-a43a66afe188
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_PREEMPTCOMMAND, DXGKARG_PREEMPTCOMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_PREEMPTCOMMAND
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGKARG_PREEMPTCOMMAND structure



## -description
The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function previously submitted to the hardware command execution unit.



## -syntax

````
typedef struct _DXGKARG_PREEMPTCOMMAND {
  UINT                     PreemptionFenceId;
  UINT                     NodeOrdinal;
  UINT                     EngineOrdinal;
  DXGK_PREEMPTCOMMANDFLAGS Flags;
} DXGKARG_PREEMPTCOMMAND;
````


## -struct-fields

### -field PreemptionFenceId

[in] A unique identifier that the display miniport driver must patch into the fence command at the end of the DMA buffer to preempt the previously submitted DMA buffer. The display miniport driver uses the identifier in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> function to inform the graphics processing unit (GPU) scheduler about the preemption at deferred-procedure-call (DPC) time.


### -field NodeOrdinal

[in] The index of the node for the preemption request. 


### -field EngineOrdinal

[in] The index of the engine for the preemption request.


### -field Flags

[in] A <a href="display.dxgk_preemptcommandflags">DXGK_PREEMPTCOMMANDFLAGS</a> structure with a reserved member or a 32-bit value. No flags are currently defined for this structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_preemptcommandflags">DXGK_PREEMPTCOMMANDFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_preemptcommand.md">DxgkDdiPreemptCommand</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_PREEMPTCOMMAND structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

