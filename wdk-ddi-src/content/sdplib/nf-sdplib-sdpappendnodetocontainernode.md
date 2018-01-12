---
UID: NF:sdplib.SdpAppendNodeToContainerNode
title: SdpAppendNodeToContainerNode function
author: windows-driver-content
description: The Bluetooth SdpAppendNodeToContainerNode function is used to attach an SDP node to a sequence or alternative SDP node.
old-location: bltooth\sdpappendnodetocontainernode.htm
old-project: bltooth
ms.assetid: beec5516-6191-4b70-8c80-ddbaedbad5c0
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: SdpAppendNodeToContainerNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdpAppendNodeToContainerNode
req.alt-loc: sdplib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PSDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpAppendNodeToContainerNode function



## -description
The Bluetooth 
  <b>SdpAppendNodeToContainerNode</b> function is used to attach an SDP node to a sequence or alternative SDP
  node.



## -syntax

````
NTSTATUS SdpAppendNodeToContainerNode(
  _In_ PSDP_NODE Parent,
  _In_ PSDP_NODE Child
);
````


## -parameters

### -param Parent [in]

The SDP sequence or alternative node to which the 
     <b>SdpAppendNodeToContainerNode</b> function adds the child node.


### -param Child [in]

The SDP node to add to the parent node.


## -returns
Possible return values include:


## -remarks
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


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sdplib.h (include BthSdpddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>
</dt>
<dt>
<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpAppendNodeToContainerNode function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

