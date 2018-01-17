---
UID: NF:dbgeng.IDebugDataSpaces4.ReadIo
title: IDebugDataSpaces4::ReadIo method
author: windows-driver-content
description: The ReadIo method reads from the system and bus I/O memory.
old-location: debugger\readio.htm
old-project: debugger
ms.assetid: d690cf53-63a6-487c-a952-07035786d19c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadIo, ReadIo
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
req.alt-api: IDebugDataSpaces.ReadIo,IDebugDataSpaces2.ReadIo,IDebugDataSpaces3.ReadIo,IDebugDataSpaces4.ReadIo
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadIo method



## -description
The <b>ReadIo</b> method reads from the system and bus I/O memory.



## -syntax

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


## -parameters

### -param InterfaceType [in]

Specifies the interface type of the I/O bus.  This parameter may take values in the INTERFACE_TYPE enumeration defined in wdm.h.


### -param BusNumber [in]

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same interface type.


### -param AddressSpace [in]

This parameter must be equal to one.


### -param Offset [in]

Specifies the I/O address within the address space.


### -param Buffer [out]

Receives the data read from the I/O bus.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.  At present, this must be 1, 2, or 4. 


### -param BytesRead [out, optional]

Receives the number of bytes returned read from the I/O bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method is only available in kernel-mode debugging.</p>