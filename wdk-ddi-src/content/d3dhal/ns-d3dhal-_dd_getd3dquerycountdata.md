---
UID: NS.D3DHAL._DD_GETD3DQUERYCOUNTDATA
title: _DD_GETD3DQUERYCOUNTDATA
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETD3DQUERYCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERYCOUNT.
old-location: display\dd_getd3dquerycountdata.htm
old-project: display
ms.assetid: 2e5877d9-a584-40fb-8e96-2ffae00df857
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_GETD3DQUERYCOUNTDATA, DD_GETD3DQUERYCOUNTDATA
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
req.alt-api: DD_GETD3DQUERYCOUNTDATA
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
---

# _DD_GETD3DQUERYCOUNTDATA structure



## -description

   DirectX 9.0 and later versions only.
   

DD_GETD3DQUERYCOUNTDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="display.dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERYCOUNT.



## -syntax

````
typedef struct _DD_GETD3DQUERYCOUNTDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwNumQueries;
} DD_GETD3DQUERYCOUNTDATA;
````


## -struct-fields

### -field gdi2

Specifies a <a href="display.dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data for the query.


### -field dwNumQueries

Receives the number of supported query types.


## -remarks
To handle D3DGDI2_TYPE_GETD3DQUERYCOUNT, the driver must store the number of query types that it supports in the <b>dwNumQueries</b> member of DD_GETD3DQUERYCOUNTDATA. Query types are represented by values in the D3DQUERYTYPE enumeration.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<dt>D3DDP2OP_CREATEQUERY</dt>
<dt>
<a href="display.dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="display.dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>
</dt>
<dt>
<a href="display.dd_getd3dquerydata">DD_GETD3DQUERYDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETD3DQUERYCOUNTDATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

