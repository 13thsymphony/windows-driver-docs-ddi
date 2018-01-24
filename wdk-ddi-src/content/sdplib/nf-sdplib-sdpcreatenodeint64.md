---
UID : NF:sdplib.SdpCreateNodeInt64
title : SdpCreateNodeInt64 function
author : windows-driver-content
description : The Bluetooth SdpCreateNodeInt64 function is used to allocate and initialize an SDP_NODE structure to a 64-bit integer type.
old-location : bltooth\sdpcreatenodeint64.htm
old-project : bltooth
ms.assetid : c6bfb1e6-9b10-4d8b-b36e-64e98c5e9080
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : SdpCreateNodeInt64
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
req.alt-api : SdpCreateNodeInt64
req.alt-loc : sdplib.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= PASSIVE_LEVEL
req.typenames : "*PSDCMD_DESCRIPTOR, SDCMD_DESCRIPTOR"
req.product : Windows 10 or later.
---


# SdpCreateNodeInt64 function
The Bluetooth 
  <b>SdpCreateNodeInt64</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to a 64-bit integer type.

## Syntax

````
PSDP_NODE SdpCreateNodeInt64(
  _In_ LONGLONG llval,
  _In_ ULONG    tag
);
````

## Parameters

`llVal`



`tag`

A profile driver defined tag to associate with the node.


## Return Value

If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.

## Remarks

After the 
    <b>SdpCreateNodeInt64</b> function allocates an 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeInt64</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.

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

<dl>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>
</dt>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>
</dt>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>
</dt>
<dt>
<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeInt64 function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>