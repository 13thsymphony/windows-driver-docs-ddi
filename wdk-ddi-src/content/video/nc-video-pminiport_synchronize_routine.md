---
UID : NC:video.PMINIPORT_SYNCHRONIZE_ROUTINE
title : PMINIPORT_SYNCHRONIZE_ROUTINE
author : windows-driver-content
description : HwVidSynchronizeExecutionCallback is an optional miniport driver function, passed in calls to VideoPortSynchronizeExecution.
old-location : display\hwvidsynchronizeexecutioncallback.htm
old-project : display
ms.assetid : 04e3bac6-c905-4c95-bd1b-e85b46c4296d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HwVidSynchronizeExecutionCallback
req.alt-loc : video.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : VHF_CONFIG, *PVHF_CONFIG
req.product : Windows 10 or later.
---


# PMINIPORT_SYNCHRONIZE_ROUTINE callback function
<i>HwVidSynchronizeExecutionCallback</i> is an optional miniport driver function, passed in calls to <b>VideoPortSynchronizeExecution</b>.

## Syntax

```
PMINIPORT_SYNCHRONIZE_ROUTINE PminiportSynchronizeRoutine;

BOOLEAN PminiportSynchronizeRoutine(
  PVOID Context
)
{...}
```

## Parameters

`Context`

Pointer to context data passed to the callback routine through <b>VideoPortSynchronizeExecution</b>. Usually, this is a pointer to the device extension or an offset within the device extension.


## Return Value

If the operation succeeds, <i>HwVidSynchronizeExecutionCallback</i> returns <b>TRUE</b>.

## Remarks

A miniport driver with one or more functions that share memory with its <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> function must have a <i>HwVidSynchronizeExecutionCallback</i> function. Any function that shares memory with <i>HwVidInterrupt</i> must call <b>VideoPortSynchronizeExecution</b> with the <i>HwVidSynchronizeExecutionCallback</i> function to maintain the integrity of data in the shared memory area. That is, only one of the <i>HwVidSynchronizeExecutionCallback</i> and <i>HwVidInterrupt</i> functions can update state in the shared area at any given moment.

The miniport driver of an adapter that does not generate interrupts also can have an <i>HwVidSynchronizeExecutionCallback</i> function to be passed to <b>VideoPortSynchronizeExecution</b> when such a driver needs to get some critical work done at a relatively high run-time priority. For example, VGA-compatible miniport drivers with <i>SvgaHwIoPortXxx</i> functions (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>) might have a <i>HwVidSynchronizeExecutionCallback</i> function that is responsible for transferring driver-buffered and validated application-issued I/O to the adapter.

<i>HwVidSynchronizeExecutionCallback</i> must not be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PMINIPORT_SYNCHRONIZE_ROUTINE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>