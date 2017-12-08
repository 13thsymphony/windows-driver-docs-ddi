---
UID: NS.winspool._BIDI_REQUEST_DATA
title: BIDI_REQUEST_DATA
author: windows-driver-content
description: The BIDI_REQUEST_DATA structure holds a single bidi request.
old-location: print\bidi_request_data.htm
old-project: print
ms.assetid: ef5a89e3-f072-48a7-b2d9-d68e0e27ba9e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: BIDI_REQUEST_DATA, BIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, *LPBIDI_REQUEST_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BIDI_REQUEST_DATA
req.alt-loc: winspool.h
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
req.product: Windows 10 or later.
---

# BIDI_REQUEST_DATA structure



## -description
<p>The BIDI_REQUEST_DATA structure holds a single bidi request.</p>


## -syntax

````
typedef struct _BIDI_REQUEST_DATA {
  DWORD     dwReqNumber;
  LPWSTR    pSchema;
  BIDI_DATA data;
} BIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, *LPBIDI_REQUEST_DATA;
````


## -struct-fields
<dl>

### -field dwReqNumber

<dd>
<p>Specifies the index of the request, which is used to match a response with a request in a multirequest operation.</p>
</dd>

### -field pSchema

<dd>
<p>Pointer to a memory location containing the first byte of the schema string.</p>
</dd>

### -field data

<dd>
<p>Specifies a <a href="..\winspool\ns-winspool--bidi-data.md">BIDI_DATA</a> structure containing the data associated with the schema.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This structure is available in Windows XP and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winspool.h (include Winspool.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\winspool\ns-winspool--bidi-data.md">BIDI_DATA</a>
</dt>
<dt>
<a href="..\winspool\ns-winspool--bidi-request-container.md">BIDI_REQUEST_CONTAINER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_REQUEST_DATA structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
