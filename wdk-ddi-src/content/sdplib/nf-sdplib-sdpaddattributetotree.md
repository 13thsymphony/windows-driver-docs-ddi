---
UID: NF:sdplib.SdpAddAttributeToTree
title: SdpAddAttributeToTree function
author: windows-driver-content
description: The Bluetooth SdpAddAttributeToTree function is used to attach an SDP attribute node to the top level of an SDP record.
old-location: bltooth\sdpaddattributetotree.htm
old-project: bltooth
ms.assetid: f5b72de2-c2e9-44ac-a2a7-04271e9253d3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpAddAttributeToTree, SdpAddAttributeToTree function [Bluetooth Devices], bltooth.sdpaddattributetotree, bth_funcs_5a46529e-8b1b-474a-a005-16f7a5562d91.xml, sdplib/SdpAddAttributeToTree
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
-	SdpAddAttributeToTree
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---


# SdpAddAttributeToTree function
The Bluetooth 
   <b>SdpAddAttributeToTree</b> function is used to attach an SDP attribute node to the top level of an SDP
  record.

## Syntax

````
NTSTATUS SdpAddAttributeToTree(
  _In_ PSDP_TREE_ROOT_NODE Root,
  _In_ USHORT              AttribId,
  _In_ PSDP_NODE           AttribValueNode,
  _In_ ULONG               tag
);
````

## Parameters

`Tree`

TBD

`AttribId`

The identifier of the attribute to attach.

`AttribValue`

TBD

`tag`

Specifies a 4-byte 
     <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


## Return Value

Possible return values include:

## Remarks

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.

For more information about the tree structure, see 
    <a href="https://msdn.microsoft.com/762cf68b-0082-4b9e-8f24-ff19ecf6f8bd">Converting SDP Records to a
    Tree Structure</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | sdplib.h (include BthSdpddi.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>