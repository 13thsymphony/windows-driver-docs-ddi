---
UID: NS.D3DUMDDI._D3DDDIARG_FINISHSESSIONKEYREFRESH
title: _D3DDDIARG_FINISHSESSIONKEYREFRESH
author: windows-driver-content
description: The D3DDDIARG_FINISHSESSIONKEYREFRESH structure contains the handle to an encryption session to end in a call to the FinishSessionKeyRefresh function.
old-location: display\d3dddiarg_finishsessionkeyrefresh.htm
old-project: display
ms.assetid: 5d262012-c4f4-4f86-a3a2-48c2fd7d5216
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDIARG_FINISHSESSIONKEYREFRESH, D3DDDIARG_FINISHSESSIONKEYREFRESH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_FINISHSESSIONKEYREFRESH is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_FINISHSESSIONKEYREFRESH
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
---

# _D3DDDIARG_FINISHSESSIONKEYREFRESH structure



## -description
The D3DDDIARG_FINISHSESSIONKEYREFRESH structure contains the handle to an encryption session to end in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function. 



## -syntax

````
typedef struct _D3DDDIARG_FINISHSESSIONKEYREFRESH {
  HANDLE hCryptoSession;
} D3DDDIARG_FINISHSESSIONKEYREFRESH;
````


## -struct-fields

### -field hCryptoSession

[in] The handle to the encryption session to end. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DDDIARG_FINISHSESSIONKEYREFRESH is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_FINISHSESSIONKEYREFRESH structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

