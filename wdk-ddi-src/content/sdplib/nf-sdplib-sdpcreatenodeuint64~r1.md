---
UID: NF.sdplib.SdpCreateNodeUInt64~r1
title: SdpCreateNodeUInt64 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUInt64 function is used to allocate and initialize an SDP_NODE structure to an unsigned 64-bit integer type.
old-location: bltooth\sdpcreatenodeuint64.htm
old-project: bltooth
ms.assetid: 17ec2944-084b-4c10-b4d2-7d291e6307bb
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: SdpCreateNodeUInt64
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
req.alt-api: SdpCreateNodeUInt64
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
req.product: Windows 10 or later.
---

# SdpCreateNodeUInt64 function



## -description
The Bluetooth 
  <b>SdpCreateNodeUInt64</b> function is used to allocate and initialize an 
  <a href="bltooth.sdp_node">SDP_NODE</a> structure to an unsigned 64-bit integer
  type.



## -syntax

````
PSDP_NODE SdpCreateNodeUInt64(
  _In_ ULONGLONG ullVal,
  _In_ ULONG     tag
);
````


## -parameters

### -param ullVal [in]

The unsigned 64-bit integer value that is used to initialize the SDP_NODE structure.


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns
If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.


## -remarks
After the 
    <b>SdpCreateNodeUInt64</b> function allocates an 
    <a href="bltooth.sdp_node">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="bltooth.sdp_node_header">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="bltooth.sdp_node_data">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeUInt64</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="bltooth.bthddi_sdp_node_interface">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.


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
<a href="bltooth.sdp_node">SDP_NODE</a>
</dt>
<dt>
<a href="bltooth.sdp_node_header">SDP_NODE_HEADER</a>
</dt>
<dt>
<a href="bltooth.sdp_node_data">SDP_NODE_DATA</a>
</dt>
<dt>
<a href="bltooth.bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeUInt64 function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

