---
UID : NF:portcls.IMiniportWaveCyclicStream.Silence
title : IMiniportWaveCyclicStream::Silence method
author : windows-driver-content
description : The Silence method is used to copy silence samples to a specified buffer.
old-location : audio\iminiportwavecyclicstream_silence.htm
old-project : audio
ms.assetid : e2acf3f5-d054-44c4-8ab9-ffd1b934f700
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IMiniportWaveCyclicStream::Silence, Silence method [Audio Devices], audio.iminiportwavecyclicstream_silence, audmp-routines_860013ac-d79b-4b11-91b7-1a7bc3c84a5b.xml, IMiniportWaveCyclicStream, IMiniportWaveCyclicStream interface [Audio Devices], Silence method, portcls/IMiniportWaveCyclicStream::Silence, Silence method [Audio Devices], IMiniportWaveCyclicStream interface, Silence
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
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
req.lib : portcls.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# Silence method
The <code>Silence</code> method is used to copy silence samples to a specified buffer.

## Syntax

````
void Silence(
  [in] PVOID Buffer,
  [in] ULONG ByteCount
);
````

## Parameters

`Buffer`

Pointer in kernel virtual-address space to the start of the buffer to which the silence samples are to be written. The buffer must be large enough to contain at least the number of bytes specified in <i>ByteCount</i>.

`ByteCount`

Specifies the number of bytes of silence to be written to the buffer.


## Return Value

<code>Silence</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

Windows treats 8-bit PCM values as unsigned, and it treats 16-bit and larger PCM values as signed. When filling a portion of an 8-bit PCM buffer with silence, the <code>Silence</code> method sets each byte to the value 0x80. When writing silence to a buffer containing 16-bit or larger PCM values, the method fills the specified portion of the buffer with zeros.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | Any level |