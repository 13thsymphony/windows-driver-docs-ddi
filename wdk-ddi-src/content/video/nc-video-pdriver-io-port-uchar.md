---
UID: NC.video.PDRIVER_IO_PORT_UCHAR
title: PDRIVER_IO_PORT_UCHAR
author: windows-driver-content
description: SvgaHwIoPortUchar traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.
old-location: display\svgahwioportuchar.htm
old-project: display
ms.assetid: 91e2dc51-0f3a-4cda-abe6-72893fd4da79
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
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
req.alt-api: SvgaHwIoPortUchar
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
req.iface: 
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_UCHAR callback



## -description
<p><i>SvgaHwIoPortUchar</i> traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending UCHAR-sized data.</p>


## -prototype

````
PDRIVER_IO_PORT_UCHAR SvgaHwIoPortUchar;

VP_STATUS SvgaHwIoPortUchar(
   ULONG_PTR Context,
   ULONG     Port,
   UCHAR     AccessMode,
   PUCHAR    Data
)
{ ... }
````


## -parameters
<dl>

### -param Context 

<dd>
<p>Specifies the miniport driver-defined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of <a href="..\video\ns-video--video-port-config-info.md">VIDEO_PORT_CONFIG_INFO</a>.</p>
</dd>

### -param Port 

<dd>
<p>Specifies the mapped I/O port to be trapped.</p>
</dd>

### -param AccessMode 

<dd>
<p>Specifies the type of access to be trapped, which can be one or a combination (ORed) of the following values:</p>
<p>
<dl>

### -param EMULATOR_READ_ACCESS


### -param EMULATOR_WRITE_ACCESS

</dl>
</p>
</dd>

### -param Data 

<dd>
<p>Pointer to the byte to be transferred.</p>
</dd>
</dl>

## -returns
<p><i>SvgaHwIoPortUchar</i> returns the final status of the operation.</p>

## -remarks
<p>Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="display.svga_functions">SVGA Functions</a>.)</p>

<p><i>SvgaHwIoPortUchar</i> intercepts any byte access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>OUT DX, AL</b> and <b>IN AL, DX</b>.</p>

<p>If the miniport driver enables the <i>Port</i> for direct access by calling <a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>, its <i>SvgaHwIoPortUchar</i> function will not be called. Such an application then will have direct access to the <i>Port</i>, unless the miniport driver disables the <i>Port</i> with another call to <b>VideoPortSetTrappedEmulatorPorts</b>.</p>

<p>If one or more application-issued x86 <b>IN</b> or <b>OUT</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.</p>

<p><i>SvgaHwIoPortUchar</i> must buffer subsequent instructions from the application to the <i>Port</i> and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUchar</i> must discard the buffered instructions. Otherwise, it should output them, a UCHAR at a time, to the specified, mapped I/O port.</p>

<p><i>SvgaHwIoPortUchar</i> should be made pageable.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\miniport\ns-miniport--emulator-access-entry.md">EMULATOR_ACCESS_ENTRY</a>
</dt>
<dt>
<a href="..\video\nc-video-pdriver-io-port-uchar-string.md">SvgaHwIoPortUcharString</a>
</dt>
<dt>
<a href="display.svga_functions">SVGA Functions</a>
</dt>
<dt>
<a href="..\video\ns-video--video-access-range.md">VIDEO_ACCESS_RANGE</a>
</dt>
<dt>
<a href="..\video\ns-video--video-port-config-info.md">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_UCHAR callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
