---
UID : NF:sdplib.SdpCreateNodeNil
title : SdpCreateNodeNil function
author : windows-driver-content
description : The Bluetooth SdpCreateNodeNil function is used to allocate and initialize an SDP_NODE structure to an empty node type.
old-location : bltooth\sdpcreatenodenil.htm
old-project : bltooth
ms.assetid : 53312cb8-a974-4394-969b-2a39def64109
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : sdplib/SdpCreateNodeNil, bltooth.sdpcreatenodenil, SdpCreateNodeNil function [Bluetooth Devices], bth_funcs_5f7d1244-67e0-436e-8658-8adcc2aa3a65.xml, SdpCreateNodeNil
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sdplib.h
req.include-header : BthSdpddi.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in Windows Vista, and later.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product : Windows 10 or later.
---


# SdpCreateNodeNil function
The Bluetooth 
  <b>SdpCreateNodeNil</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to an empty node type.

## Syntax

````
PSDP_NODE SdpCreateNodeNil(
  _In_ ULONG tag
);
````

## Parameters

`tag`

A profile driver defined tag to associate with the node.


## Return Value

If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.

## Remarks

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sdplib.h (include BthSdpddi.h) |
| **Library** |  |
| **IRQL** | <= PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeNil function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>