---
UID: NC:video.PDRIVER_IO_PORT_ULONG
title: PDRIVER_IO_PORT_ULONG
author: windows-driver-content
description: SvgaHwIoPortUlong traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.
old-location: display\svgahwioportulong.htm
old-project: display
ms.assetid: e749188f-a255-403a-8ae9-a2c3c9b41c58
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PDRIVER_IO_PORT_ULONG, SvgaHwIoPortUlong, SvgaHwIoPortUlong callback function [Display Devices], VideoMiniport_Functions_84ae9115-8192-469a-b3c1-536d3964d906.xml, display.svgahwioportulong, video/SvgaHwIoPortUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	SvgaHwIoPortUlong
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PDRIVER_IO_PORT_ULONG callback function
<i>SvgaHwIoPortUlong</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.

## Syntax

```
PDRIVER_IO_PORT_ULONG PdriverIoPortUlong;

VP_STATUS PdriverIoPortUlong(
  ULONG_PTR Context,
  ULONG Port,
  UCHAR AccessMode,
  PULONG Data
)
{...}
```

## Parameters

`Context`

Specifies the miniport driver-determined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of VIDEO_PORT_CONFIG_INFO.

`Port`

Specifies the mapped I/O port to be trapped.

`AccessMode`

Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>

`Data`

Pointer to the ULONG data to be transferred.


## Return Value

<i>SvgaHwIoPortUlong</i> returns the final status of the operation.

## Remarks

Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)

<i>SvgaHwIoPortUlong</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, EAX</b> and <b>IN EAX, DX</b>.

If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUlong</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the range with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUlong</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUlong</i> must discard the buffered instructions. Otherwise, it should output them, a ULONG at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUlong</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>



<a href="..\dispmprt\ns-dispmprt-_emulator_access_entry.md">EMULATOR_ACCESS_ENTRY</a>



<a href="..\video\nc-video-pdriver_io_port_ulong_string.md">SvgaHwIoPortUlongString</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_ULONG callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>