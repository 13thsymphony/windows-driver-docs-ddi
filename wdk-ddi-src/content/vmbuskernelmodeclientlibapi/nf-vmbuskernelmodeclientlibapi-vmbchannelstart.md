---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelStart
title: VmbChannelStart function
author: windows-driver-content
description: The VmbChannelStart function moves a channel out of the paused state.
old-location: netvista\vmbchannelstart.htm
old-project: netvista
ms.assetid: A318FD24-4E48-4DE4-B919-DD1D701F7EA7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: vmbuskernelmodeclientlibapi/VmbChannelStart, VmbChannelStart function [Network Drivers Starting with Windows Vista], VmbChannelStart, netvista.vmbchannelstart
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	vmbkmcl.lib
-	vmbkmcl.dll
apiname:
-	VmbChannelStart
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelStart function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelStart</b> function moves a channel out of the paused state.

## Syntax

````
VOID VmbChannelStart(
  _In_ VMBCHANNEL Channel
);
````

## Parameters

`Channel`

A handle for a channel that this function modifies.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |