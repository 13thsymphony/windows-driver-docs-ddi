---
UID: NF.dbgeng.IDebugDataSpaces4.WriteBusData
title: IDebugDataSpaces4::WriteBusData method
author: windows-driver-content
description: The WriteBusData method writes data to a system bus.
old-location: debugger\writebusdata.htm
old-project: Debugger
ms.assetid: bd4e762d-b3d5-4a4c-bdeb-998cd72783b4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::WriteBusData, WriteBusData
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
req.alt-api: IDebugDataSpaces.WriteBusData,IDebugDataSpaces2.WriteBusData,IDebugDataSpaces3.WriteBusData,IDebugDataSpaces4.WriteBusData
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
---

# IDebugDataSpaces4::WriteBusData method



## -description
The <b>WriteBusData</b> method writes data to a system bus.



## -syntax

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


## -parameters

### -param BusDataType [in]

Specifies the bus data type of the bus to write to.  For details of allowed values see the documentation for the BUS_DATA_TYPE enumeration in the Microsoft Windows SDK.


### -param BusNumber [in]

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.


### -param SlotNumber [in]

Specifies the logical slot number on the bus.


### -param Offset [in]

Specifies the offset in the bus data to start writing to.


### -param Buffer [in]

Specifies the data to write to the bus.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes written to the bus.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is only available in kernel-mode debugging.

The nature of the data read from the bus is system, bus, and slot dependent.


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