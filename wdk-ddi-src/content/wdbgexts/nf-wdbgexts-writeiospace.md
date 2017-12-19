---
UID: NF.wdbgexts.WriteIoSpace
title: WriteIoSpace function
author: windows-driver-content
description: The WriteIoSpace function writes to the system I/O locations.
old-location: debugger\writeiospace.htm
old-project: Debugger
ms.assetid: 4d1a3df6-2440-46b7-8e73-f017f5fcfa51
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WriteIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WriteIoSpace
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
req.product: Windows 10 or later.
---

# WriteIoSpace function



## -description
The <b>WriteIoSpace</b> function writes to the system I/O locations. 



## -syntax

````
VOID  WriteIoSpace(
   ULONG  address,
   ULONG  data,
   PULONG size
);
````


## -parameters

### -param address 

Specifies the I/O address to write to.


### -param data 

Specifies the address of a variable that holds the data to write. This must be at least the number of bytes contained in <i>size</i>.


### -param size 

Specifies the address of a variable that contains the number of bytes to write. <i>Size</i> must be 1, 2, or 4. After the data is written, <i>size</i> will contain the number of bytes actually written.


## -returns
None


## -remarks
If you are writing 64-bit code, you should use <a href="debugger.writeiospace64">WriteIoSpace64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>