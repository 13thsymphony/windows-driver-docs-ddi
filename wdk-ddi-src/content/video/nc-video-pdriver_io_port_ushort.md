---
UID: NC.video.PDRIVER_IO_PORT_USHORT
title: PDRIVER_IO_PORT_USHORT
author: windows-driver-content
description: SvgaHwIoPortUshort traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.
old-location: display\svgahwioportushort.htm
old-project: display
ms.assetid: 304656b4-ebbe-4cb1-8735-2e03bec71f9f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
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
req.alt-api: SvgaHwIoPortUshort
req.alt-loc: video.h
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
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_USHORT callback



## -description
<i>SvgaHwIoPortUshort</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of USHORT-sized data.


## -prototype

````
PDRIVER_IO_PORT_USHORT SvgaHwIoPortUshort;

VP_STATUS SvgaHwIoPortUshort(
   ULONG_PTR Context,
   ULONG     Port,
   UCHAR     AccessMode,
   PUSHORT   Data
)
{ ... }
````


## -parameters

### -param Context 

Specifies the miniport driver-determined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of VIDEO_PORT_CONFIG_INFO.

### -param Port 

Specifies the mapped I/O port to be trapped.

### -param AccessMode 

Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:


### -param EMULATOR_READ_ACCESS
### -param EMULATOR_WRITE_ACCESS



### -param Data 

Pointer to the USHORT data to be transferred.

## -returns
<i>SvgaHwIoPortUshort</i> returns the final status of the operation.

## -remarks
Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="display.svga_functions">SVGA Functions</a>.)

<i>SvgaHwIoPortUshort</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, AX</b> and <b>IN AX, DX</b>.

If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUshort</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUshort</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUshort</i> must discard the buffered instructions. Otherwise, it should output them, a USHORT at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUshort</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.emulator_access_entry">EMULATOR_ACCESS_ENTRY</a>
</dt>
<dt>
<a href="display.svga_functions">SVGA Functions</a>
</dt>
<dt>
<a href="..\video\nc-video-pdriver_io_port_ushort_string.md">SvgaHwIoPortUshortString</a>
</dt>
<dt>
<a href="display.video_access_range">VIDEO_ACCESS_RANGE</a>
</dt>
<dt>
<a href="display.video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="display.videoportsettrappedemulatorports">VideoPortSetTrappedEmulatorPorts</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_USHORT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
