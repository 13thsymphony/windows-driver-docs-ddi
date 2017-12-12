---
UID: NC.bthsdpddi.PCONVERTSTREAMTOTREE
title: PCONVERTSTREAMTOTREE
author: windows-driver-content
description: The Bluetooth SdpConvertStreamToTree function is used to create a Microsoft proprietary tree-based representation of an SDP record, while leaving the original stream-based representation unmodified.
old-location: bltooth\sdpconvertstreamtotree.htm
old-project: bltooth
ms.assetid: 3b285a32-c1bc-4103-aa2e-0f6c8f5cc7ec
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdpConvertStreamToTree
req.alt-loc: BthSdpddi.h
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
---

# PCONVERTSTREAMTOTREE callback



## -description
The Bluetooth 
  <b>SdpConvertStreamToTree</b> function is used to create a Microsoft proprietary tree-based representation
  of an SDP record, while leaving the original stream-based representation unmodified.



## -prototype

````
PCONVERTSTREAMTOTREE SdpConvertStreamToTree;

NTSTATUS SdpConvertStreamToTree(
   PUCHAR              Stream,
   ULONG               Size,
   PSDP_TREE_ROOT_NODE Node,
   ULONG               tag
)
{ ... }
````


## -parameters

### -param Stream 

The SDP record stream to convert into a tree-based representation.


### -param Size 

The size of the source SDP record stream.


### -param Node 

A pointer to the 
     <a href="bltooth.sdp_tree_root_node">SDP_TREE_ROOT_NODE</a> structure that serves
     as the root of the SDP tree-based representation of the SDP record.


### -param tag 

Specifies a 4-byte 
     <a href="wdkgloss.p#wdkgloss.pool_tag#wdkgloss.pool_tag"><i>pool tag</i></a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>.


## -returns
Possible return values include:


<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INSUFFICIENT_RESOURCES
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>

<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INSUFFICIENT_RESOURCES
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>

## -remarks
Because a tree can be traversed by evaluating pointers, the 
    <b>SdpConvertStreamToTree</b> function can make it easier for profile drivers to extract information from
    an SDP record.

The tree representation of the SDP record that results from calling the 
    <b>SdpConvertStreamToTree</b> function consists of a series of interconnected 
    <a href="bltooth.sdp_node">SDP_NODE</a> structures. The root node contains a single
    SDP_TREE_ROOT_NODE structure.

Each SDP_NODE structure contains an 
    <a href="bltooth.sdp_node_header">SDP_NODE_HEADER</a> structure and an 
    <a href="bltooth.sdp_node_data">SDP_NODE_DATA</a> union. The header specifies the
    type of data, and Bluetooth profile drivers can access links to peer SDP_NODE structures through the 
    <a href="kernel.list_entry">LIST_ENTRY</a> system structure. By evaluating this
    structure's 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that the pointers in the LIST_ENTRY structure hold addresses to other
    LIST_ENTRY structures, and that Bluetooth drivers must use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.

By using the 
    <a href="bltooth.sdp_node_data">SDP_NODE_DATA</a> union's 
    <b>sequence</b> and 
    <b>alternative</b> members, profile drivers can access sub-elements of the tree. If the data type of the
    node is 
    <b>SDP_TYPE_SEQUENCE</b>, the node is an SDP sequence. If the data type of the node is 
    <b>SDP_TYPE_ALTERNATIVE</b>, the node is an SDP alternative sequence. In the first case, the sequence
    member is valid and contains the information necessary to access the portion of the tree corresponding
    with the sequnce. In the second case, the alternative member is valid and contains the information
    necessary to access the portion of the tree corresponding to the alternative. The 
    <b>sequence</b> or 
    <b>alternative</b> member, when used, contains an extra SDP_NODE_HEADER structure that is used to access
    the nodes in the sequence or alternative. For example, 
    <code>node-&gt;u.sequence.Flink</code>points to the LIST_ENTRY structure of
    the first member of the sequence represented by the node.

The remaining members of the data union contain actual data extracted from the SDP stream. For most
    types, the data is directly present in the structure. However, for strings and URLs, a pointer is
    provided to the actual data. The memory for the string is allocated by the 
    <b>SdpConvertStreamToTree</b> function call and must be freed by calling the 
    <a href="bltooth.sdpfreetree">SdpFreeTree</a> function for the tree.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="bltooth.bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.


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
<dt>BthSdpddi.h (include BthSdpddi.h)</dt>
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
<a href="bltooth.sdp_tree_root_node">SDP_TREE_ROOT_NODE</a>
</dt>
<dt>
<a href="bltooth.sdp_node">SDP_NODE</a>
</dt>
<dt>
<a href="bltooth.sdp_node_header">SDP_NODE_HEADER</a>
</dt>
<dt>
<a href="bltooth.sdp_node_data">SDP_NODE_DATA</a>
</dt>
<dt>
<a href="kernel.list_entry">LIST_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>
</dt>
<dt>
<a href="bltooth.sdpfreetree">SdpFreeTree</a>
</dt>
<dt>
<a href="bltooth.bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PCONVERTSTREAMTOTREE callback function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

