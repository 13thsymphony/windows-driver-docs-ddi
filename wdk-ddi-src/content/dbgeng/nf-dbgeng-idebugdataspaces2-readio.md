---
UID: NF:dbgeng.IDebugDataSpaces2.ReadIo
title: IDebugDataSpaces2::ReadIo method
author: windows-driver-content
description: The ReadIo method reads from the system and bus I/O memory.
old-location: debugger\readio.htm
old-project: debugger
ms.assetid: d690cf53-63a6-487c-a952-07035786d19c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging], ReadIo method, IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], ReadIo method, IDebugDataSpaces2::ReadIo, IDebugDataSpaces3 interface [Windows Debugging], ReadIo method, IDebugDataSpaces3::ReadIo, IDebugDataSpaces4 interface [Windows Debugging], ReadIo method, IDebugDataSpaces4::ReadIo, IDebugDataSpaces::ReadIo, IDebugDataSpaces_a6189a47-dc48-44cf-aadd-61769085ebc5.xml, ReadIo method [Windows Debugging], ReadIo method [Windows Debugging], IDebugDataSpaces interface, ReadIo method [Windows Debugging], IDebugDataSpaces2 interface, ReadIo method [Windows Debugging], IDebugDataSpaces3 interface, ReadIo method [Windows Debugging], IDebugDataSpaces4 interface, ReadIo,IDebugDataSpaces2.ReadIo, dbgeng/IDebugDataSpaces2::ReadIo, dbgeng/IDebugDataSpaces3::ReadIo, dbgeng/IDebugDataSpaces4::ReadIo, dbgeng/IDebugDataSpaces::ReadIo, debugger.readio
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces.ReadIo
-	IDebugDataSpaces2.ReadIo
-	IDebugDataSpaces3.ReadIo
-	IDebugDataSpaces4.ReadIo
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ReadIo method
The <b>ReadIo</b> method reads from the system and bus I/O memory.

## Syntax

````
HRESULT ReadIo(
  [in]            ULONG   InterfaceType,
  [in]            ULONG   BusNumber,
  [in]            ULONG   AddressSpace,
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````

## Parameters

`InterfaceType`

Specifies the interface type of the I/O bus.  This parameter may take values in the INTERFACE_TYPE enumeration defined in wdm.h.

`BusNumber`

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same interface type.

`AddressSpace`

This parameter must be equal to one.

`Offset`

Specifies the I/O address within the address space.

`Buffer`

Receives the data read from the I/O bus.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.  At present, this must be 1, 2, or 4.

`BytesRead`

Receives the number of bytes returned read from the I/O bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method is only available in kernel-mode debugging.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |