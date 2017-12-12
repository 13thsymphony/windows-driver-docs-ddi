---
UID: NS.D3DUMDDI._D3DDDI_ISSUEQUERYFLAGS
title: _D3DDDI_ISSUEQUERYFLAGS
author: windows-driver-content
description: The D3DDDI_ISSUEQUERYFLAGS structure identifies the state of a query issue.
old-location: display\d3dddi_issuequeryflags.htm
old-project: display
ms.assetid: 68360c2e-4b03-40a3-a313-bdb9ef26a298
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDI_ISSUEQUERYFLAGS, D3DDDI_ISSUEQUERYFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_ISSUEQUERYFLAGS
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

# _D3DDDI_ISSUEQUERYFLAGS structure



## -description
The D3DDDI_ISSUEQUERYFLAGS structure identifies the state of a query issue.



## -syntax

````
typedef struct _D3DDDI_ISSUEQUERYFLAGS {
  union {
    struct {
      UINT Begin  :1;
      UINT End  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3DDDI_ISSUEQUERYFLAGS;
````


## -struct-fields

### -field Begin

A UINT value that specifies whether to start the query issue. The Microsoft Direct3D runtime does not request query data while in this state.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field End

A UINT value that specifies whether to end the query issue and transition the state to subsignaled. Results of the query are not available until the state transitions to signaled.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_ISSUEQUERYFLAGS that can hold one 32-bit value that identifies the state of the query.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="display.d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ISSUEQUERYFLAGS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

