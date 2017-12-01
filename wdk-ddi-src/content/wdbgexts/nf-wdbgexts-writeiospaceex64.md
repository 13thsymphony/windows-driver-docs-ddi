---
UID: NF.wdbgexts.WriteIoSpaceEx64
title: WriteIoSpaceEx64
author: windows-driver-content
description: The WriteIoSpaceEx64 function is an extended version of WriteIoSpace64.
old-location: debugger\writeiospaceex64.htm
old-project: debugger
ms.assetid: 4fc874ab-b31d-41ae-baeb-18819c4e3970
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: WriteIoSpaceEx64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WriteIoSpaceEx64
req.alt-loc: wdbgexts.h
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

# WriteIoSpaceEx64 function



## -description
<p>The <b>WriteIoSpaceEx64</b> function is an extended version of <a href="..\wdbgexts\nf-wdbgexts-writeiospace64.md">WriteIoSpace64</a>. It can write to either a system I/O location or an I/O location on a bus. <b>WriteIoSpace64</b> works like <b>WriteIoSpaceEx64</b>, except that it defaults <i>interfacetype</i> to ISA, <i>busnumber</i> to zero, and <i>addressspace</i> to 1.</p>


## -syntax

````
VOID  WriteIoSpaceEx64(
   ULONG64 address,
   ULONG   data,
   PULONG  size,
   ULONG   interfacetype,
   ULONG   busnumber,
   ULONG   addressspace
);
````


## -parameters
<dl>

### -param <i>address</i> 

<dd>
<p>Specifies the I/O address to write to.</p>
</dd>

### -param <i>data</i> 

<dd>
<p>Specifies the address of a variable that holds the data to write. This must be at least the number of bytes contained in <i>size</i>.</p>
</dd>

### -param <i>size</i> 

<dd>
<p>Specifies the address of a variable that contains the number of bytes to write. <i>Size</i> must be 1, 2, or 4. After the data is written, <i>size</i> will contain the number of bytes actually written.</p>
</dd>

### -param <i>interfacetype</i> 

<dd>
<p>Specifies the type of interface on which the extended I/O space exists. Possible values include ISA, EISA, and MCA. For more information, see ntddk.h, which is available as part of the Windows Driver Kit.</p>
</dd>

### -param <i>busnumber</i> 

<dd>
<p>Specifies the number of the bus on which the extended I/O space exists. This is typically zero, unless there is more than one bus of a given type.</p>
</dd>

### -param <i>addressspace</i> 

<dd>
<p>This is typically 1.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If you are writing 32-bit code, you should use <a href="..\wdbgexts\nf-wdbgexts-writeiospaceex.md">WriteIoSpaceEx</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.</p>

<p>For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.</p>

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
<dt>Wdbgexts.h (include Wdbgexts.h, Wdbgexts.h, or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>