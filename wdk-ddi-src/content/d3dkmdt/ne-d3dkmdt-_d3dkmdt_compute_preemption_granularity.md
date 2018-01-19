---
UID : NE:d3dkmdt._D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
title : _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
author : windows-driver-content
description : Specifies the capabilities for the preemption of graphic processing unit (GPU) compute shader operations that the display miniport driver supports.
old-location : display\d3dkmdt_compute_preemption_granularity.htm
old-project : display
ms.assetid : d8ed5406-3b76-49a7-961c-0be737b1dda9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY, D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
req.alt-loc : D3dkmdt.h
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
req.typenames : D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
---

# _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY Enumeration
Specifies the capabilities for the preemption of graphic processing unit (GPU) compute shader operations that the display miniport driver supports.

## Syntax
````
typedef enum _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY { 
  D3DKMDT_COMPUTE_PREEMPTION_NONE                   = 0,
  D3DKMDT_COMPUTE_PREEMPTION_DMA_BUFFER_BOUNDARY    = 100,
  D3DKMDT_COMPUTE_PREEMPTION_DISPATCH_BOUNDARY      = 200,
  D3DKMDT_COMPUTE_PREEMPTION_THREAD_GROUP_BOUNDARY  = 300,
  D3DKMDT_COMPUTE_PREEMPTION_THREAD_BOUNDARY        = 400,
  D3DKMDT_COMPUTE_PREEMPTION_SHADER_BOUNDARY        = 500
} D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY;
````

## Constants

<table>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_DISPATCH_BOUNDARY</td>
<td>The driver cannot stop currently executing compute shader commands that were dispatched from a thread group but can prevent all pending commands from being dispatched.</td>
</tr>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_DMA_BUFFER_BOUNDARY</td>
<td>The driver cannot stop currently running DMA buffers of a specified type but can prevent all pending DMA buffers in the hardware queue from running.</td>
</tr>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_NONE</td>
<td>The driver does not support the preemption of GPU compute shader operations.

<div class="alert"><b>Note</b>  This value also specifies that the driver cannot stop currently running DMA buffers of a specified type and cannot prevent all pending DMA buffers in the hardware queue from running.</div>
<div> </div></td>
</tr>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_SHADER_BOUNDARY</td>
<td>The driver cannot stop currently running shader commands of a specified type but can prevent all shader commands in the hardware queue from running.</td>
</tr>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_THREAD_BOUNDARY</td>
<td>The driver cannot stop currently executing compute shader commands that were dispatched from a thread in a thread group but can prevent a thread from dispatching other commands.</td>
</tr>

<tr>
<td>D3DKMDT_COMPUTE_PREEMPTION_THREAD_GROUP_BOUNDARY</td>
<td>The driver cannot stop currently executing compute shader commands that were dispatched from a thread group but can prevent a thread group from dispatching other commands.</td>
</tr>
</table>

## Remarks

Starting with Windows 8, display miniport drivers need to specify the level of preemption granularity supported by the GPU when executing compute shader operations. Because  engines on the same adapter may potentially support different preemption levels, the driver should report the coarsest granularity among all engines capable of executing a particular type of compute shader requests. 

For example, if one engine supports the preemption of primitive level graphics requests, and another engine supports the preemption of triangle level graphics requests, the driver should report primitive level graphics preemption capability for that adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<dl>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_graphics_preemption_granularity.md">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_preemption_caps.md">D3DKMDT_PREEMPTION_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>