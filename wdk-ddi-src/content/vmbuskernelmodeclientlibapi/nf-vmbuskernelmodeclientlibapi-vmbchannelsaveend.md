---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSaveEnd
title: VmbChannelSaveEnd function
author: windows-driver-content
description: The VmbChannelSaveEnd function cleans up any resources that were allocated for saving state of a channel.
old-location: netvista\vmbchannelsaveend.htm
old-project: netvista
ms.assetid: 0E61AF98-DC71-4234-B337-71B2AF65D858
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: VmbChannelSaveEnd
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
req.alt-api: VmbChannelSaveEnd
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelSaveEnd function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveEnd</b> function cleans up any resources that were allocated for saving state of a channel.



## -syntax

````
VOID VmbChannelSaveEnd(
  _In_ VMBCHANNEL Channel
    
);
````


## -parameters

### -param Channel
    </i> [in]
<dd>
A handle of the channel that was saved. 


## -returns
This function does not return a value.


## -remarks
