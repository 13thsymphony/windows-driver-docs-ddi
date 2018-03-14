---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelPause
title: VmbChannelPause function
author: windows-driver-content
description: The VmbChannelPause function moves a channel into the paused state, which prevents new I/O.
old-location: netvista\vmbchannelpause.htm
old-project: netvista
ms.assetid: 434CA5F7-24D4-40E7-AE77-C0732D3FBBFF
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbChannelPause, VmbChannelPause function [Network Drivers Starting with Windows Vista], netvista.vmbchannelpause, vmbuskernelmodeclientlibapi/VmbChannelPause
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelPause
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelPause function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPause</b>  function moves a channel into the paused state, which prevents new I/O.

## Syntax

````
VOID VmbChannelPause(
  _In_ VMBCHANNEL Channel
);
````

## Parameters

`Channel`

A handle for the channel to pause.


## Return Value

This function does not return a value.

## Remarks

This function waits until the channel is in the paused state before it returns. This ensures that all packets that are waiting for completion have completed.


 If the channel is disabled, this function sets the channel to automatically
pause when it is enabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |