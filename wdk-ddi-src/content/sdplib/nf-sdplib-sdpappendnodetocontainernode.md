---
UID: NF:sdplib.SdpAppendNodeToContainerNode
title: SdpAppendNodeToContainerNode function
author: windows-driver-content
description: The Bluetooth SdpAppendNodeToContainerNode function is used to attach an SDP node to a sequence or alternative SDP node.
old-location: bltooth\sdpappendnodetocontainernode.htm
old-project: bltooth
ms.assetid: beec5516-6191-4b70-8c80-ddbaedbad5c0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpAppendNodeToContainerNode, SdpAppendNodeToContainerNode function [Bluetooth Devices], bltooth.sdpappendnodetocontainernode, bth_funcs_dce0f01b-3dab-48d4-8230-ad3bb0d1c210.xml, sdplib/SdpAppendNodeToContainerNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdplib.h
api_name:
-	SdpAppendNodeToContainerNode
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---


# SdpAppendNodeToContainerNode function
The Bluetooth 
  <b>SdpAppendNodeToContainerNode</b> function is used to attach an SDP node to a sequence or alternative SDP
  node.

## Syntax

````
NTSTATUS SdpAppendNodeToContainerNode(
  _In_ PSDP_NODE Parent,
  _In_ PSDP_NODE Child
);
````

## Parameters

`Parent`

The SDP sequence or alternative node to which the 
     <b>SdpAppendNodeToContainerNode</b> function adds the child node.

`Node`

TBD


## Return Value

Possible return values include:

## Remarks

Use the 
    <b>SdpAppendNodeToContainerNode</b> function to insert any type of 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> into a sequence or alternative node,
    including other sequences.

Do not use this function to attach attribute nodes to the top level of an SDP record. Call the 
    <a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a> function to
    perform that action. For more information about the tree structure, see 
    <a href="https://msdn.microsoft.com/762cf68b-0082-4b9e-8f24-ff19ecf6f8bd">Converting SDP Records to a
    Tree Structure</a>.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | sdplib.h (include BthSdpddi.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>