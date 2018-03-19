---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT
author: windows-driver-content
description: Contains a response from the QueryAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_query_output.htm
old-project: display
ms.assetid: 1e5d5b29-ecda-48be-b4fe-e3a153f2e0e2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT, display.d3d11_1ddi_authenticated_query_output
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
-	D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT structure
Contains a response from the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> function.

## Syntax
````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT {
  D3D11_1DDI_OMAC omac;
  GUID            QueryType;
  HANDLE          hChannel;
  UINT            SequenceNumber;
  HRESULT         ReturnCode;
} D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT;
````

## Members


`omac`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a> structure that contains a Message Authentication Code (MAC) of the data. The driver uses Advanced Encryption Standard (AES)-based one-key CBC MAC (OMAC) to calculate this value for the block of data that appears after this structure member.

`QueryType`

A GUID that specifies the query. For a list of possible values, see the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure.

`hChannel`

A handle to the authenticated channel. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.

`SequenceNumber`

The query sequence number.

`ReturnCode`

The return code that the driver returns when the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> function is called.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>