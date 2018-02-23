---
UID: NF:dbgeng.IDebugDataSpaces3.ReadBusData
title: IDebugDataSpaces3::ReadBusData method
author: windows-driver-content
description: The ReadBusData method reads data from a system bus.
old-location: debugger\readbusdata.htm
old-project: Debugger
ms.assetid: 5790b133-dbdc-4f77-a70e-616b0902794e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugDataSpaces4::ReadBusData, ReadBusData, IDebugDataSpaces interface [Windows Debugging], ReadBusData method, IDebugDataSpaces2::ReadBusData, IDebugDataSpaces3 interface [Windows Debugging], ReadBusData method, ReadBusData method [Windows Debugging], IDebugDataSpaces2 interface [Windows Debugging], ReadBusData method, ReadBusData method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces4 interface [Windows Debugging], ReadBusData method, dbgeng/IDebugDataSpaces2::ReadBusData, IDebugDataSpaces::ReadBusData, IDebugDataSpaces3, IDebugDataSpaces_59d5bf3f-7eb5-452c-ace2-4aed701d34a6.xml, ReadBusData method [Windows Debugging], IDebugDataSpaces interface, debugger.readbusdata, dbgeng/IDebugDataSpaces::ReadBusData, ReadBusData method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces, dbgeng/IDebugDataSpaces4::ReadBusData, dbgeng/IDebugDataSpaces3::ReadBusData, IDebugDataSpaces2, IDebugDataSpaces3::ReadBusData, ReadBusData method [Windows Debugging], IDebugDataSpaces4 interface
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces.ReadBusData
-	IDebugDataSpaces2.ReadBusData
-	IDebugDataSpaces3.ReadBusData
-	IDebugDataSpaces4.ReadBusData
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ReadBusData method
The <b>ReadBusData</b> method reads data from a system bus.

## Syntax

````
HRESULT ReadBusData(
  [in]            ULONG  BusDataType,
  [in]            ULONG  BusNumber,
  [in]            ULONG  SlotNumber,
  [in]            ULONG  Offset,
  [out]           PVOID  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG BytesRead
);
````

## Parameters

`BusDataType`

Specifies the bus data type to read from.  For details of allowed values see the documentation for the BUS_DATA_TYPE enumeration in the Microsoft Windows SDK.

`BusNumber`

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.

`SlotNumber`

Specifies the logical slot number on the bus.

`Offset`

Specifies the offset in the bus data to start reading from.

`Buffer`

Receives the data from the bus.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.

`BytesRead`

Receives the number of bytes read from the bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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

The nature of the data read from the bus is system, bus, and slot dependent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |