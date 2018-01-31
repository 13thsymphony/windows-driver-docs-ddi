---
UID : NF:minitape.TapeClassAllocateSrbBuffer
title : TapeClassAllocateSrbBuffer function
author : windows-driver-content
description : The TapeClassAllocateSrbBuffer routine allocates an Srb-&gt;DataBuffer.
old-location : storage\tapeclassallocatesrbbuffer.htm
old-project : storage
ms.assetid : f6762d9b-5a3d-49a3-b954-48e4e4a9eacb
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : tapeclas_77717175-fd25-4cbe-8baf-8c326a5ec152.xml, TapeClassAllocateSrbBuffer, storage.tapeclassallocatesrbbuffer, minitape/TapeClassAllocateSrbBuffer, TapeClassAllocateSrbBuffer routine [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : minitape.h
req.include-header : Minitape.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Tape.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PTAPE_STATUS, TAPE_STATUS"
---


# TapeClassAllocateSrbBuffer function
The <b>TapeClassAllocateSrbBuffer</b> routine allocates an <b>Srb-&gt;DataBuffer</b>.

## Syntax

````
BOOLEAN TapeClassAllocateSrbBuffer(
  _Inout_ PSCSI_REQUEST_BLOCK Srb,
  _In_    ULONG               SrbBufferSize
);
````

## Parameters

`Srb`

Pointer to the SRB.

`SrbBufferSize`

Specifies the size, in bytes, of the <b>DataBuffer</b> to be allocated.


## Return Value

<b>TapeClassAllocateSrbBuffer </b>returns <b>TRUE</b> if the <b>DataBuffer</b> was allocated successfully, and <b>FALSE</b> if the buffer was not allocated.

## Remarks

<b>TapeClassAllocateSrbBuffer </b>allocates an <b>Srb-&gt;DataBuffer</b> from nonpaged memory and initializes the members to zero. If the buffer already exists from an earlier call, it is freed and a new buffer allocated. A tape miniclass driver calls this routine to allocate a <b>DataBuffer</b> in a portable way.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | minitape.h (include Minitape.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |