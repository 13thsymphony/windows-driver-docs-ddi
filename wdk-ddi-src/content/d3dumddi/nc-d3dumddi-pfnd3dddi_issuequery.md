---
UID: NC:d3dumddi.PFND3DDDI_ISSUEQUERY
title: PFND3DDDI_ISSUEQUERY
author: windows-driver-content
description: The IssueQuery function processes a query.
old-location: display\issuequery.htm
old-project: display
ms.assetid: e31b2b6a-3721-472a-8044-6516a8419ad3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IssueQuery
req.alt-loc: d3dumddi.h
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_ISSUEQUERY callback



## -description
The <i>IssueQuery</i> function processes a query.



## -prototype

````
PFND3DDDI_ISSUEQUERY IssueQuery;

__checkReturn HRESULT APIENTRY IssueQuery(
  _In_       HANDLE               hDevice,
  _In_ const D3DDDIARG_ISSUEQUERY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_issuequery.md">D3DDDIARG_ISSUEQUERY</a> structure that describes how to process the query.


## -returns
<i>IssueQuery</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The query is successfully processed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>IssueQuery</i> could not allocate the required memory for it to complete.

 


## -remarks
 The user-mode display driver should set a fence value and store the fence value in the driver's private query structure. The user-mode display driver implements the query by using a fence. If the <i>IssueQuery</i> function is called on a query again before a previous query issue completes, the driver should overwrite the fence value and ignore the previous query issue.

If the call to <i>IssueQuery</i> requires the driver to return data, the driver should insert a graphics processing unit (GPU) instruction to write the required data to an allocation. In the call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getquerydata.md">GetQueryData</a> function, the driver should typically lock the allocation and return the appropriate data.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_issuequery.md">D3DDDIARG_ISSUEQUERY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getquerydata.md">GetQueryData</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_ISSUEQUERY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

