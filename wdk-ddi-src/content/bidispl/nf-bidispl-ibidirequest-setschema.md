---
UID: NF.bidispl.IBidiRequest.SetSchema
title: IBidiRequest::SetSchema method
author: windows-driver-content
description: The IBidiRequest::SetSchema method sets the bidi schema string.
old-location: print\ibidirequest_ibidirequest__setschema.htm
old-project: print
ms.assetid: ca4f7ea4-fcad-42b0-a63a-eee3706e5cbf
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IBidiRequest, IBidiRequest::SetSchema, SetSchema
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IBidiRequest.IBidiRequest::SetSchema
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
req.irql: 
---

# IBidiRequest::SetSchema method



## -description
The <b>IBidiRequest::SetSchema</b> method sets the bidi schema string.



## -syntax

````
HRESULT IBidiRequest::SetSchema(
  [in] const LPCWSTR pszSchema
);
````


## -parameters

### -param pszSchema [in]

Pointer to a schema string.


## -returns
The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation was successfully carried out.
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>The interface handle was invalid.
<dl>
<dt><b>None of the above</b></dt>
</dl>The <b>HRESULT</b> contains an error code corresponding to the last error.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows XP

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2003

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bidispl.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::IBidiRequest::SetSchema method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

