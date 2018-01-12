---
UID: NS:d3dkmthk._D3DKMT_FENCE_PRESENTHISTORYTOKEN
title: _D3DKMT_FENCE_PRESENTHISTORYTOKEN
author: windows-driver-content
description: The D3DKMT_FENCE_PRESENTHISTORYTOKEN structure identifies a fence present-history operation.
old-location: display\d3dkmt_fence_presenthistorytoken.htm
old-project: display
ms.assetid: a27371cf-08d2-4502-b766-3b9c60272080
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_FENCE_PRESENTHISTORYTOKEN, D3DKMT_FENCE_PRESENTHISTORYTOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_FENCE_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_FENCE_PRESENTHISTORYTOKEN
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_FENCE_PRESENTHISTORYTOKEN
---

# _D3DKMT_FENCE_PRESENTHISTORYTOKEN structure



## -description
The D3DKMT_FENCE_PRESENTHISTORYTOKEN structure identifies a fence present-history operation.



## -syntax

````
typedef struct _D3DKMT_FENCE_PRESENTHISTORYTOKEN {
  UINT64 Key;
} D3DKMT_FENCE_PRESENTHISTORYTOKEN;
````


## -struct-fields

### -field Key

[in] A 64-bit value that specifies the key for the fence. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DKMT_FENCE_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FENCE_PRESENTHISTORYTOKEN structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

