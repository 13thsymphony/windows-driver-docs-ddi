---
UID : NF:video.VideoPortReadRegisterBufferUshort
title : VideoPortReadRegisterBufferUshort function
author : windows-driver-content
description : The VideoPortReadRegisterBufferUshort function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.
old-location : display\videoportreadregisterbufferushort.htm
old-project : display
ms.assetid : 5a8e0be5-8eed-47f1-88df-43f3776def7f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortReadRegisterBufferUshort
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VideoPortReadRegisterBufferUshort
req.alt-loc : Videoprt.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : See Remarks section.
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortReadRegisterBufferUshort function
The <b>VideoPortReadRegisterBufferUshort</b> function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.

## Syntax

````
VOID VideoPortReadRegisterBufferUshort(
        PUSHORT Register,
  _Out_ PUSHORT Buffer,
        ULONG   Count
);
````

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer into which the USHORT values are written.

`Count`

Specifies the number of USHORT values to be written to the buffer.


## Return Value

None

## Remarks

The buffer must be large enough to contain at least the specified number of USHORT values.

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterBufferUshort</b>.

Callers of <b>VideoPortReadRegisterBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReadRegisterBufferUshort function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>