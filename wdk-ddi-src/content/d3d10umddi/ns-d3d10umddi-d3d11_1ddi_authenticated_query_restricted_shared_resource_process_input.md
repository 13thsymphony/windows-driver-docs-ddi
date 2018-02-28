---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_INPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS.
old-location: display\d3d11_1ddi_authenticated_query_restricted_shared_resource_process_input.htm
old-project: display
ms.assetid: a4b18099-aff8-4709-a040-838e1391cedc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT, display.d3d11_1ddi_authenticated_query_restricted_shared_resource_process_input
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
-	D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT structure
Contains the response to a <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS</b>.

## Syntax
````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_INPUT Input;
  UINT                                 ProcessIndex;
} D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT;
````

## Members


`Input`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure that contains the GUID for the query and other data.

`ProcessIndex`

The index of the process.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>