---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelRestoreFromBuffer
title : VmbChannelRestoreFromBuffer function
author : windows-driver-content
description : The VmbChannelRestoreFromBuffer function restores the client state from previously saved state. The driver must check the return value of the function.
old-location : netvista\vmbchannelrestorefrombuffer.htm
old-project : netvista
ms.assetid : 5A063585-AC45-44DF-BE21-FA1BB6283E6F
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : VmbChannelRestoreFromBuffer
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.alt-api : VmbChannelRestoreFromBuffer
req.alt-loc : VmbusKernelModeClientLibApi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# VmbChannelRestoreFromBuffer function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelRestoreFromBuffer</b>  function restores the client state from previously saved state.
The driver must check the return value of the function.

## Syntax

````
NTSTATUS VmbChannelRestoreFromBuffer(
  _In_ VMBCHANNEL                        Channel,
  _In_ reads_bytes_(BufferSize)    PVOID Buffer,
  _In_ ULONG                             BufferSize
);
````

## Parameters

`Channel`

A handle for a channel.

`Buffer`

A pointer to a buffer that contains previously saved state.

`BufferSize`

The size, in bytes, of the buffer.


## Return Value

<b>VmbChannelRestoreFromBuffer</b> returns one of the following status values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function finished successfully.
<dl>
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>State was restored successfully,     but more chunks were saved.
<dl>
<dt><b>Other status code for which NT_SUCCESS is FALSE</b></dt>
</dl>The function failed.

## Remarks

The caller is expected to call this function with buffers that contain whole
"chunks" of stored data.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |