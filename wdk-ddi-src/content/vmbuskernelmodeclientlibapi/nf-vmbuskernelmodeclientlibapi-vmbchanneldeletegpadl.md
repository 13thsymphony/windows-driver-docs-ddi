---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelDeleteGpadl
title : VmbChannelDeleteGpadl function
author : windows-driver-content
description : The VmbChannelDeleteGpadl function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the VmbChannelCreateGpadlFromMdl or VmbChannelCreateGpadlFromBuffer functions.
old-location : netvista\vmbchanneldeletegpadl.htm
old-project : netvista
ms.assetid : B1446A29-F2C1-4F08-8B38-5BE9188F5132
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : VmbChannelDeleteGpadl function [Network Drivers Starting with Windows Vista], vmbuskernelmodeclientlibapi/VmbChannelDeleteGpadl, VmbChannelDeleteGpadl, netvista.vmbchanneldeletegpadl
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Vmbkmcl.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product : Windows 10 or later.
---


# VmbChannelDeleteGpadl function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelDeleteGpadl</b> function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrommdl.md">VmbChannelCreateGpadlFromMdl</a> or
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrombuffer.md">VmbChannelCreateGpadlFromBuffer</a> functions. If the GPADL is currently mapped to the server, this function is blocked until the GPADL is unmapped.

## Syntax

````
VOID VmbChannelDeleteGpadl(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     GpadlHandle
);
````

## Parameters

`Channel`

A handle for a channel.

`GpadlHandle`

The GPADL handle of the GPADL to delete.


## Return Value

This function does not return a value.


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

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrommdl.md">VmbChannelCreateGpadlFromMdl</a>

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrombuffer.md">VmbChannelCreateGpadlFromBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelDeleteGpadl function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>