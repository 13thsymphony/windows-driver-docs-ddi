---
UID: NF:dbgeng.IDebugDataSpaces4.GetOffsetInformation
title: IDebugDataSpaces4::GetOffsetInformation method
author: windows-driver-content
description: The GetOffsetInformation method provides general information about an address in a process's data space.
old-location: debugger\getoffsetinformation.htm
old-project: debugger
ms.assetid: 5ef00c92-7b32-473a-8401-4c02e864c181
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::GetOffsetInformation, GetOffsetInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces4.GetOffsetInformation
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugDataSpaces4::GetOffsetInformation method



## -description
The <b>GetOffsetInformation</b> method provides general information about an address in a process's data space.



## -syntax

````
HRESULT GetOffsetInformation(
  [in]            ULONG   Space,
  [in]            ULONG   Which,
  [in]            ULONG64 Offset,
  [out, optional] PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  InfoSize
);
````


## -parameters

### -param Space [in]

Specifies the data space to which the <i>Offset </i>parameter applies.  The allowed values depend on the <i>Which</i> parameter.


### -param Which [in]

Specifies which information about the data is being queried.  This determines the possible values for <i>Space</i> and the type of the data returned in <i>Buffer</i>.  Possible values are:




### -param DEBUG_OFFSINFO_VIRTUAL_SOURCE

Returns the source of the target's virtual memory at <i>Offset</i>.  This is where the debugger engine reads the memory from.  <i>Space</i> must be set to DEBUG_DATA_SPACE_VIRTUAL.  A ULONG is returned to <i>Buffer</i>.  This ULONG can take the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_VSOURCE_INVALID

</td>
<td>
The <i>Offset</i> offset is not available in the process's virtual address space.

This could mean that the address is invalid, or that the memory is unavailable -- for example, a crash-dump file might not contain all of the memory for the process or for the kernel.

</td>
</tr>
<tr>
<td>
DEBUG_VSOURCE_DEBUGGEE

</td>
<td>
The virtual memory at the <i>Offset</i> offset is provided by the target.

</td>
</tr>
<tr>
<td>
DEBUG_VSOURCE_MAPPED_IMAGE

</td>
<td>
The debugger engine reads the target's virtual memory at <i>Offset </i>offset from a local image file.  This is often the case in minidump files where the module images are not included in the dump file and are instead loaded by the debugger engine.

</td>
</tr>
</table>
 

</dd>
</dl>

### -param Offset [in]

Specifies the offset in the target's data space for which the information is returned.


### -param Buffer [out, optional]

Specifies the buffer to receive the information.  The type of the data returned depends on the value of <i>Which</i>.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in bytes, of the <i>Buffer </i>buffer.


### -param InfoSize [out, optional]

Receives the size, in bytes, of the information that is returned.  If <i>InfoSize</i> is <b>NULL</b>, this information is not returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>