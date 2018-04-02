---
UID: NS:d3dumddi._D3DDDIARG_QUERYAUTHENICATEDCHANNEL
title: "_D3DDDIARG_QUERYAUTHENICATEDCHANNEL"
author: windows-driver-content
description: The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the QueryAuthenticatedChannel function.
old-location: display\d3dddiarg_queryauthenticatedchannel.htm
old-project: display
ms.assetid: d816b4d7-cc99-4a83-9fd2-c7c0659d0318
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_5c16c40f-b8b6-41cc-9f83-f204d7213760.xml, _D3DDDIARG_QUERYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, display.d3dddiarg_queryauthenticatedchannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_QUERYAUTHENICATEDCHANNEL structure
The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the <a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a> function.

## Syntax
```
typedef struct _D3DDDIARG_QUERYAUTHENICATEDCHANNEL {
  UINT       InputSize;
  const VOID *pInputData;
  UINT       OutputSize;
  VOID       *pOutputData;
} D3DDDIARG_QUERYAUTHENTICATEDCHANNEL;
```

## Members


`InputSize`

[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to.

`pInputData`

[in] A pointer to a buffer that describes the information to query. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Query</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Query</b>, see the Windows SDK documentation.

`OutputSize`

[in] The size, in bytes, of the output data that the <b>pOutputData</b> member points to.

`pOutputData`

[in/out] A pointer to a buffer that describes the information that the <a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a> function returns. The buffer that <b>pOutputData</b> points to is defined identically to the output buffer that the <b>IDirect3DAuthenticatedChannel::Query</b> method returns.

## Remarks
The definitions of the input and output buffers to which the <b>pInputData</b> and <b>pOutputData</b> members point, depend on the type of information. The first member of the input buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure, whose <b>QueryType</b> member identifies the type of information to query.

The definition of the output buffer also depends on the information that the <a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a> function queries. However, the first member of the output buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_OUTPUT structure, whose members specify the following information:

<ul>
<li>
The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that permits the caller to authenticate the entire buffer, which prevents man-in-the-middle attacks.

</li>
<li>
The <b>QueryType</b>, <b>hChannel</b>, and <b>SequenceNumber</b> members from the input buffer prevent against replay attacks. 

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_QUERYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system. D3DDDIARG_QUERYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a>