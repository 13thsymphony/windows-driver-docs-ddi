---
UID: NC.d3d10umddi.PFND3D10DDI_CREATEQUERY
title: PFND3D10DDI_CREATEQUERY
author: windows-driver-content
description: The CreateQuery(D3D10) function creates a query.
old-location: display\createquery_d3d10_.htm
old-project: display
ms.assetid: abe6a82f-1613-4c74-9e81-01939db74bfd
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateQuery
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

# PFND3D10DDI_CREATEQUERY callback



## -description
<p>The <b>CreateQuery(D3D10)</b> function creates a query.</p>


## -prototype

````
PFND3D10DDI_CREATEQUERY CreateQuery;

VOID APIENTRY CreateQuery(
  _In_       D3D10DDI_HDEVICE        hDevice,
  _In_ const D3D10DDIARG_CREATEQUERY *pCreateQuery,
  _In_       D3D10DDI_HQUERY         hQuery,
  _In_       D3D10DDI_HRTQUERY       hRTQuery
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pCreateQuery</i> [in]

<dd>
<p> A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createquery.md">D3D10DDIARG_CREATEQUERY</a> structure that describes the parameters that the user-mode display driver uses to create a query. </p>
</dd>

### -param <i>hQuery</i> [in]

<dd>
<p> A handle to the driver's private data for the query. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-calcprivatequerysize.md">CalcPrivateQuerySize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its query object. </p>
</dd>

### -param <i>hRTQuery</i> [in]

<dd>
<p> A handle to the query that the driver should use anytime it calls back into the Direct3D runtime. </p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.</p>

## -remarks
<p>The driver might run out of memory or be unable to create queries because of their exclusive nature. Therefore, the driver can pass E_OUTOFMEMORY, DXGI_DDI_ERR_NONEXCLUSIVE, or D3DDDIERR_DEVICEREMOVED in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-destroyquery.md">DestroyQuery(D3D10)</a> function to destroy the handle that the <i>hQuery</i> parameter specifies.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi-devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createquery.md">D3D10DDIARG_CREATEQUERY</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-destroyquery.md">DestroyQuery(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEQUERY callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
