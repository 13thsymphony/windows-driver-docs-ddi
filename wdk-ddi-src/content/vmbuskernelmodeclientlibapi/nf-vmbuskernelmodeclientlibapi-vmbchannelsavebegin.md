---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSaveBegin
title: VmbChannelSaveBegin function
author: windows-driver-content
description: The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function.
old-location: netvista\vmbchannelsavebegin.htm
old-project: netvista
ms.assetid: A0946287-3ED2-4DE1-A3D7-46611B25BB93
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: vmbuskernelmodeclientlibapi/VmbChannelSaveBegin, VmbChannelSaveBegin, netvista.vmbchannelsavebegin, VmbChannelSaveBegin function [Network Drivers Starting with Windows Vista]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	VmbChannelSaveBegin
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---


# VmbChannelSaveBegin function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveBegin</b> function initializes the context for saving the state of a channel. The driver must check the return value of the function.

## Syntax

````
NTSTATUS VmbChannelSaveBegin(
  _In_ VMBCHANNEL Channel
    
);
````

## Parameters

`Channel`

A handle for the channel to save.


## Return Value

<b>VmbChannelSaveBegin</b> returns a status code.

## Remarks

The
caller next calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue.md"> VmbChannelSaveContinue</a>

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend.md">VmbChannelSaveEnd</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelSaveBegin function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>