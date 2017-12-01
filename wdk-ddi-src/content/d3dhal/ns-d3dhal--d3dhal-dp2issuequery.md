---
UID: NS.d3dhal._D3DHAL_DP2ISSUEQUERY
title: D3DHAL_DP2ISSUEQUERY
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2issuequery.htm
old-project: display
ms.assetid: e7870f7a-545e-43eb-99c5-42a740585c43
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2ISSUEQUERY, D3DHAL_DP2ISSUEQUERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2ISSUEQUERY
req.alt-loc: d3dhal.h
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

# D3DHAL_DP2ISSUEQUERY structure



## -description
<p>
   DirectX 9.0 and later versions only.
   </p>
<p>One or more D3DHAL_DP2ISSUEQUERY structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_ISSUEQUERY, and are used to query for various types of information.</p>


## -syntax

````
typedef struct _D3DHAL_DP2ISSUEQUERY {
  DWORD dwQueryID;
  DWORD dwFlags;
} D3DHAL_DP2ISSUEQUERY, *LPD3DHAL_DP2ISSUEQUERY;
````


## -struct-fields
<dl>

### -field <b>dwQueryID</b>

<dd>
<p>Identifies the query for which the driver asynchronously provides information.</p>
</dd>

### -field <b>dwFlags</b>

<dd>
<p>Specifies the state of the query. This member can contain one or more of the following flags: </p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>
<dl>

### -field D3DISSUE_BEGIN


### -field (1 &lt;&lt; 1)

</dl>
</p>
</td>
<td>
<p>Starts building the query. The runtime does not request query data while in this state.</p>
</td>
</tr>
<tr>
<td>
<p>
<dl>

### -field D3DISSUE_END


### -field (1 &lt;&lt; 0)

</dl>
</p>
</td>
<td>
<p>Transitions the state to subsignaled. Results of the query are not available until the state transitions to signaled.</p>
</td>
</tr>
</table>
<p> </p>
<p>The driver can ignore query requests with <b>dwFlags</b> set to 0. </p>
</dd>
</dl>

## -remarks
<p>The runtime uses D3DHAL_DP2ISSUEQUERY to identify each query that the driver must process. The driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2ISSUEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and retrieves information associated with the queries that they represent. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>D3DDP2OP_ISSUEQUERY</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2createquery.md">D3DHAL_DP2CREATEQUERY</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2responsequery.md">D3DHAL_DP2RESPONSEQUERY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2ISSUEQUERY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
