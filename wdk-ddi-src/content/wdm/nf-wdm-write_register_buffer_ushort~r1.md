---
UID: NF.wdm.WRITE_REGISTER_BUFFER_USHORT~r1
title: WRITE_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register.
old-location: kernel\write_register_buffer_ushort.htm
old-project: kernel
ms.assetid: 070fc2b0-045e-4778-82d4-0850cd2064a5
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WRITE_REGISTER_BUFFER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WRITE_REGISTER_BUFFER_USHORT
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
req.product: Windows 10 or later.
---

# WRITE_REGISTER_BUFFER_USHORT function



## -description
The <b>WRITE_REGISTER_BUFFER_USHORT</b> routine writes a number of USHORT values from a buffer to the specified register. 



## -syntax

````
VOID WRITE_REGISTER_BUFFER_USHORT(
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````


## -parameters

### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

Pointer to a buffer from which an array of USHORT values is to be written.


### -param Count [in]

Specifies the number of USHORT values to be written to the register. 


## -returns
None


## -remarks
The size of the buffer must be large enough to contain at least the specified number of USHORT values.

Callers of <b>WRITE_REGISTER_BUFFER_USHORT</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (see Remarks section)

</td>
</tr>
</table>