---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE.
old-location: display\d3d11_1ddi_authenticated_query_channel_type_output.htm
old-project: display
ms.assetid: 2bdcc511-c176-4f8f-83fe-7a3715b60330
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT, display.d3d11_1ddi_authenticated_query_channel_type_output
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT structure
Contains the response to a <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE</b>.

## Syntax
````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT Output;
  D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE ChannelType;
} D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT;
````

## Members


`Output`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.

`ChannelType`

A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type.md">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> value that specifies the channel type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type.md">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>