---
UID : NF:sdplib.SdpAppendNodeToContainerNode
title : SdpAppendNodeToContainerNode function
author : windows-driver-content
description : The Bluetooth SdpAppendNodeToContainerNode function is used to attach an SDP node to a sequence or alternative SDP node.
old-location : bltooth\sdpappendnodetocontainernode.htm
old-project : bltooth
ms.assetid : beec5516-6191-4b70-8c80-ddbaedbad5c0
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : sdplib/SdpAppendNodeToContainerNode, SdpAppendNodeToContainerNode, SdpAppendNodeToContainerNode function [Bluetooth Devices], bltooth.sdpappendnodetocontainernode, bth_funcs_dce0f01b-3dab-48d4-8230-ad3bb0d1c210.xml
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
    <mshelp:link keywords="bltooth.converting_sdp_records_to_a_tree_structure" tabindex="0">Converting SDP Records to a
    Tree Structure</mshelp:link>.

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

<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpAppendNodeToContainerNode function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>