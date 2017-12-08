---
UID: NF.bidispl.IBidiRequest.GetResult
title: IBidiRequest::GetResult
author: windows-driver-content
description: The IBidiRequest::GetResult method tells whether the bidi request was successful.
old-location: print\ibidirequest_ibidirequest__getresult.htm
old-project: print
ms.assetid: d3d37fd2-b3fa-4664-ba4b-c355197d9b40
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IBidiRequest, GetResult, IBidiRequest::GetResult
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IBidiRequest.IBidiRequest::GetResult
req.alt-loc: bidispl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: Bidispl.dll
req.irql: PASSIVE_LEVEL
req.iface: IBidiRequest
---

# IBidiRequest::GetResult method



## -description
<p>The <b>IBidiRequest::GetResult</b> method tells whether the bidi request was successful.</p>


## -syntax

````
HRESULT IBidiRequest::GetResult(
  [out] HRESULT *phr
);
````


## -parameters
<dl>

### -param phr [out]

<dd>
<p>Pointer to a variable that specifies the status of the bidi request.</p>
</dd>
</dl>

## -returns
<p>The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The operation was successfully carried out.</p><dl>
<dt><b>E_HANDLE</b></dt>
</dl><p>The interface handle was invalid.</p><dl>
<dt><b>E_POINTER</b></dt>
</dl><p>At least one of the pointer variable parameters did not reference a valid memory location.</p><dl>
<dt><b>None of the above</b></dt>
</dl><p>The <b>HRESULT</b> contains an error code corresponding to the last error.</p>

<p> </p>

<p>Note that the return value indicates whether the method was successful. It does not indicate what happened to the bidi request.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows XP</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2003</p>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bidispl.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Bidispl.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.bidirectional_communication_interfaces">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>
</dt>
<dt>
<a href="..\bidispl\nn-bidispl-ibidirequest.md">IBidiRequest</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::IBidiRequest::GetResult method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
