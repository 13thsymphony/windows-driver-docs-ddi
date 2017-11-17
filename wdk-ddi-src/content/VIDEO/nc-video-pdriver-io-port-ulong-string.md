---
UID: NC.video.PDRIVER_IO_PORT_ULONG_STRING
title: PDRIVER_IO_PORT_ULONG_STRING
author: windows-driver-content
description: SvgaHwIoPortUlongString traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.
old-location: display\svgahwioportulongstring.htm
ms.assetid: 190adc75-7274-49e2-a9b6-2897168df091
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SvgaHwIoPortUlongString
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
ms.keywords: VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
req.iface: 
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_ULONG_STRING callback



## -description
<p><i>SvgaHwIoPortUlongString</i> traps an I/O port range to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of ULONG-sized data.</p>


## -prototype

````
PDRIVER_IO_PORT_ULONG_STRING SvgaHwIoPortUlongString;

VP_STATUS SvgaHwIoPortUlongString(
   ULONG_PTR Context,
   ULONG     Port,
   UCHAR     AccessMode,
   PULONG    Data,
   ULONG     DataLength
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> 

<dd>
<p>Specifies the miniport driver-determined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of VIDEO_PORT_CONFIG_INFO.</p>
</dd>

### -param <i>Port</i> 

<dd>
<p>Specifies the mapped I/O port to be trapped.</p>
</dd>

### -param <i>AccessMode</i> 

<dd>
<p>Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:</p>
<p>
<dl>

### -param EMULATOR_READ_ACCESS


### -param EMULATOR_WRITE_ACCESS

</dl>
</p>
</dd>

### -param <i>Data</i> 

<dd>
<p>Pointer to the ULONG data string to be transferred. The string is hooked out one value at a time until it is all used.</p>
</dd>

### -param <i>DataLength</i> 

<dd>
<p>Specifies the number of ULONG values in the string.</p>
</dd>
</dl>

## -returns
<p><i>SvgaHwIoPortUlongString</i> returns the final status of the operation.</p>

## -remarks
<p>Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)</p>

<p><i>SvgaHwIoPortUlongString</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>REP OUTSD DX, ESI</b> and <b>REP INSD EDI, DX</b>.</p>

<p>If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUlongString</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.</p>

<p>If one or more application-issued x86 <b>INSD</b> or <b>OUTSD</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.</p>

<p><i>SvgaHwIoPortUlongString</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUlongString</i> must discard the buffered instructions. Otherwise, it should output them, a ULONG at a time, to the specified, mapped I/O port.</p>

<p><i>SvgaHwIoPortUlongString</i> should be made pageable.</p>

<p>Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)</p>

<p><i>SvgaHwIoPortUlongString</i> intercepts any range access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>REP OUTSD DX, ESI</b> and <b>REP INSD EDI, DX</b>.</p>

<p>If the miniport driver enables the <i>Port</i> range for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUlongString</i> function will not be called. Such an application then will have direct access to the I/O port range, unless the miniport driver disables the <i>Port</i> range with another call to <b>VideoSetTrappedEmulatorPorts</b>.</p>

<p>If one or more application-issued x86 <b>INSD</b> or <b>OUTSD</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.</p>

<p><i>SvgaHwIoPortUlongString</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUlongString</i> must discard the buffered instructions. Otherwise, it should output them, a ULONG at a time, to the specified, mapped I/O port.</p>

<p><i>SvgaHwIoPortUlongString</i> should be made pageable.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564131">EMULATOR_ACCESS_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e749188f-a255-403a-8ae9-a2c3c9b41c58">SvgaHwIoPortUlong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570366">VideoPortSetTrappedEmulatorPorts</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDRIVER_IO_PORT_ULONG_STRING callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
