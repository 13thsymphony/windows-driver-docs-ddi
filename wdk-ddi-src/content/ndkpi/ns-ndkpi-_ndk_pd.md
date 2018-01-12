---
UID: NS:ndkpi._NDK_PD
title: _NDK_PD
author: windows-driver-content
description: The NDK_PD structure specifies the attributes of an NDK protection domain (PD) object.
old-location: netvista\ndk_pd.htm
old-project: netvista
ms.assetid: 77D3503A-8544-4E73-AD17-56F9C8603068
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDK_PD, NDK_PD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_PD
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: NDK_PD
---

# _NDK_PD structure



## -description
The <b>NDK_PD</b> structure specifies the attributes of an NDK protection domain (PD) object.



## -syntax

````
typedef struct _NDK_PD {
  NDK_OBJECT_HEADER     Header;
  CONST NDK_PD_DISPATCH *Dispatch;
} NDK_PD, *PNDK_PD;
````


## -struct-fields

### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_PD</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypePd</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_pd_dispatch.md">NDK_PD_DISPATCH</a> structure that defines dispatch functions for the NDK PD object.


## -remarks
An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_pd_dispatch.md">NDK_PD_DISPATCH</a> table before returning the  created PD object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_pd_dispatch.md">NDK_PD_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_pd.md">NDK_FN_CREATE_PD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_PD structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

