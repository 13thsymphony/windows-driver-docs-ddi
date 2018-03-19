---
UID: NF:sdplib.SdpCreateNodeBoolean
title: SdpCreateNodeBoolean function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeBoolean function is used to allocate and initialize an SDP_NODE structure to a Boolean type.
old-location: bltooth\sdpcreatenodeboolean.htm
old-project: bltooth
ms.assetid: d299074f-18db-4eff-b177-4d2d3535e299
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpCreateNodeBoolean, SdpCreateNodeBoolean function [Bluetooth Devices], bltooth.sdpcreatenodeboolean, bth_funcs_06168a9c-1cdc-4c2a-b90d-356c03867d4f.xml, sdplib/SdpCreateNodeBoolean
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
-	SdpCreateNodeBoolean
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---


# SdpCreateNodeBoolean function
The Bluetooth 
  <b>SdpCreateNodeBoolean</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to a Boolean type.

## Syntax

````
PSDP_NODE SdpCreateNodeBoolean(
  _In_ SDP_BOOLEAN bVal,
  _In_ ULONG       tag
);
````

## Parameters

`bVal`

The Boolean value that is used to initialize the SDP_NODE structure.

`tag`

A profile driver defined tag to associate with the node.


## Return Value

If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.

## Remarks

The data associated with the 
    <b>SdpCreateNodeBoolean</b> function is copied into the node, and the original data can be freed at any
    time.

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

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>