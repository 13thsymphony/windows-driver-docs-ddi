---
UID: NS.d3dhal._D3DHAL_CONTEXTDESTROYDATA
title: D3DHAL_CONTEXTDESTROYDATA
author: windows-driver-content
description: The D3DHAL_CONTEXTDESTROYDATA structure contains the information that the D3dContextDestroy function requires to delete a context.
old-location: display\d3dhal_contextdestroydata.htm
old-project: display
ms.assetid: 1224f634-b349-4098-a6ad-cbf18742ffb7
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_CONTEXTDESTROYDATA, D3DHAL_CONTEXTDESTROYDATA
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
req.alt-api: D3DHAL_CONTEXTDESTROYDATA
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

# D3DHAL_CONTEXTDESTROYDATA structure



## -description
<p>The D3DHAL_CONTEXTDESTROYDATA structure contains the information that the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextdestroycb.md">D3dContextDestroy</a> function requires to delete a context.</p>


## -syntax

````
typedef struct _D3DHAL_CONTEXTDESTROYDATA {
  ULONG_PTR dwhContext;
  HRESULT   ddrval;
} D3DHAL_CONTEXTDESTROYDATA, *LPD3DHAL_CONTEXTDESTROYDATA;
````


## -struct-fields
<dl>

### -field <b>dwhContext</b>

<dd>
<p>Specifies the handle to the context to be destroyed.</p>
</dd>

### -field <b>ddrval</b>

<dd>
<p>Specifies the location where the driver writes the return code for <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextdestroycb.md">D3dContextDestroy</a>. D3D_OK indicates success. For more information, see <a href="https://msdn.microsoft.com/033beb6e-5872-4cb3-8f39-459e2fff82cd">Return Codes for Direct3D Driver Callbacks</a>.</p>
</dd>
</dl>

## -remarks


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
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextdestroycb.md">D3dContextDestroy</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_CONTEXTDESTROYDATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
