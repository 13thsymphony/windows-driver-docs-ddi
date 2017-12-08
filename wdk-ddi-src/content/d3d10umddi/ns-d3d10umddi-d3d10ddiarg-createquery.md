---
UID: NS.d3d10umddi.D3D10DDIARG_CREATEQUERY
title: D3D10DDIARG_CREATEQUERY
author: windows-driver-content
description: The D3D10DDIARG_CREATEQUERY structure describes the query to create.
old-location: display\d3d10ddiarg_createquery.htm
old-project: display
ms.assetid: 1042f401-fbdd-47ee-8cfc-1bca331ac722
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10DDIARG_CREATEQUERY, D3D10DDIARG_CREATEQUERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_CREATEQUERY
req.alt-loc: d3d10umddi.h
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
req.iface: 
---

# D3D10DDIARG_CREATEQUERY structure



## -description
<p>The D3D10DDIARG_CREATEQUERY structure describes the query to create.</p>


## -syntax

````
typedef struct D3D10DDIARG_CREATEQUERY {
  D3D10DDI_QUERY Query;
  UINT           MiscFlags;
} D3D10DDIARG_CREATEQUERY;
````


## -struct-fields
<dl>

### -field Query

<dd>
<p>[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi-query.md">D3D10DDI_QUERY</a>-typed value that identifies the type of query to create. </p>
</dd>

### -field MiscFlags

<dd>
<p>[in] A valid bitwise OR of flag values for the query. Currently, the Direct3D runtime supports only the D3D10DDI_QUERY_MISCFLAG_PREDICATEHINT (0x1) flag. This flag is set along with a D3DQUERYTYPE_OCCLUSIONPREDICATE query type to indicate that the predicate query is a hint. If a predicate query is indicated as a hint (versus guaranteed), no result is ever propagated back to the calling application. </p>
</dd>
</dl>

## -remarks
<p>The Direct3D runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createquery.md">CreateQuery(D3D10)</a> function with a query type to create resources for a query. For information about the type of resources the user-mode display driver creates, see the values of the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi-query.md">D3D10DDI_QUERY</a> enumeration.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-calcprivatequerysize.md">CalcPrivateQuerySize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createquery.md">CreateQuery(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi-query.md">D3D10DDI_QUERY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATEQUERY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
