---
UID: NF:dbgeng.IDebugDataSpaces3.WriteBusData
title: IDebugDataSpaces3::WriteBusData method
author: windows-driver-content
description: The WriteBusData method writes data to a system bus.
old-location: debugger\writebusdata.htm
old-project: debugger
ms.assetid: bd4e762d-b3d5-4a4c-bdeb-998cd72783b4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging], WriteBusData method, IDebugDataSpaces2 interface [Windows Debugging], WriteBusData method, IDebugDataSpaces2::WriteBusData, IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], WriteBusData method, IDebugDataSpaces3::WriteBusData, IDebugDataSpaces4 interface [Windows Debugging], WriteBusData method, IDebugDataSpaces4::WriteBusData, IDebugDataSpaces::WriteBusData, IDebugDataSpaces_a1fb8543-dee8-475d-b42c-17077d72b06e.xml, WriteBusData method [Windows Debugging], WriteBusData method [Windows Debugging], IDebugDataSpaces interface, WriteBusData method [Windows Debugging], IDebugDataSpaces2 interface, WriteBusData method [Windows Debugging], IDebugDataSpaces3 interface, WriteBusData method [Windows Debugging], IDebugDataSpaces4 interface, WriteBusData,IDebugDataSpaces3.WriteBusData, dbgeng/IDebugDataSpaces2::WriteBusData, dbgeng/IDebugDataSpaces3::WriteBusData, dbgeng/IDebugDataSpaces4::WriteBusData, dbgeng/IDebugDataSpaces::WriteBusData, debugger.writebusdata
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
req.lib: 
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
-	IDebugDataSpaces.WriteBusData
-	IDebugDataSpaces2.WriteBusData
-	IDebugDataSpaces3.WriteBusData
-	IDebugDataSpaces4.WriteBusData
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WriteBusData method
The <b>WriteBusData</b> method writes data to a system bus.

## Syntax

````
HRESULT WriteBusData(
  [in]            ULONG  BusDataType,
  [in]            ULONG  BusNumber,
  [in]            ULONG  SlotNumber,
  [in]            ULONG  Offset,
  [in]            PVOID  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG BytesWritten
);
````

## Parameters

`BusDataType`

Specifies the bus data type of the bus to write to.  For details of allowed values see the documentation for the BUS_DATA_TYPE enumeration in the Microsoft Windows SDK.

`BusNumber`

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.

`SlotNumber`

Specifies the logical slot number on the bus.

`Offset`

Specifies the offset in the bus data to start writing to.

`Buffer`

Specifies the data to write to the bus.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.

`BytesWritten`

Receives the number of bytes written to the bus.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

## Remarks

This method is only available in kernel-mode debugging.

The nature of the data read from the bus is system, bus, and slot dependent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |