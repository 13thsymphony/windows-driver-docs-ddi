---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetMaximumExternalData
title: VmbChannelInitSetMaximumExternalData function
author: windows-driver-content
description: The VmbChannelInitSetMaximumExternalData function sets the maximum size and chain length of data that is described by a packet, but not directly sent in the packet. That is, the maximum size of the buffer described by an ExternalDataMdl.
old-location: netvista\vmbchannelinitsetmaximumexternaldata.htm
old-project: netvista
ms.assetid: 558E8162-7B1F-41AB-A04C-113E94C97DB6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: VmbChannelInitSetMaximumExternalData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbChannelInitSetMaximumExternalData
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetMaximumExternalData function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetMaximumExternalData</b> function sets the maximum size and chain length of data that is described by a
packet, but not directly sent in the packet. That is, the maximum size of the
buffer described by an <b>ExternalDataMdl</b>.  



## -syntax

````
NTSTATUS VmbChannelInitSetMaximumExternalData(
  _In_ VMBCHANNEL         Channel,
  _In_ range_(>,0) UINT32 DataSize,
  _In_ range_(>,0) UINT32 ChainLength
);
````


## -parameters

### -param Channel [in]

A pointer to a Kernel Mode Client Library (KMCL) channel.



### -param DataSize [in]

The maximum size of external data.



### -param ChainLength [in]

The maximum number of Memory Descriptor Lists (MDLs) in an incoming MDL chain.


## -returns
<b>VmbChannelInitSetMaximumExternalData</b> can return one of the following status values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function finished successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The <i>DataSize</i> value is invalid. Zero (0) is invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>The <i>ChainLength</i> value is  invalid. Zero (0) is invalid.

 

 KMCL ensures
that your ring buffers are large enough to send packets that contain
buffers in the specified limits.


## -remarks
