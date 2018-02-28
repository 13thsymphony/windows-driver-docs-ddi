---
UID: NF:bidispl.IBidiRequest.SetInputData
title: IBidiRequest::SetInputData method
author: windows-driver-content
description: The SetInputData method sets the data to send to the printer.
old-location: print\ibidirequest_ibidirequest__setinputdata.htm
old-project: print
ms.assetid: 8db7b5cd-b03f-4973-8711-8ac022bfb2b5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, IBidiRequest, IBidiRequest interface [Print Devices], SetInputData method, IBidiRequest::SetInputData, SetInputData method [Print Devices], SetInputData method [Print Devices], IBidiRequest interface, SetInputData,IBidiRequest.SetInputData, _win32_IBidiRequest_SetInputData, bidispl/IBidiRequest::SetInputData, gdi.ibidirequest_ibidirequest__setinputdata, print.ibidirequest_ibidirequest__setinputdata
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: bidispl.h
req.dll: Bidispl.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiRequest.SetInputData
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# SetInputData method
The <b>SetInputData</b> method sets the data to send to the printer.

## Syntax

````
HRESULT SetInputData(
  [in] const DWORD dwType,
  [in] const BYTE  *pData,
  [in] const UINT  uSize
);
````

## Parameters

`dwType`

The type of data to be sent. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="BIDI_NULL"></a><a id="bidi_null"></a><dl>
<dt><b>BIDI_NULL</b></dt>
</dl>
</td>
<td width="60%">
No data.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_INT"></a><a id="bidi_int"></a><dl>
<dt><b>BIDI_INT</b></dt>
</dl>
</td>
<td width="60%">
Integer data.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_FLOAT"></a><a id="bidi_float"></a><dl>
<dt><b>BIDI_FLOAT</b></dt>
</dl>
</td>
<td width="60%">
Floating-point number.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BOOL"></a><a id="bidi_bool"></a><dl>
<dt><b>BIDI_BOOL</b></dt>
</dl>
</td>
<td width="60%">
<b>TRUE</b> or <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_STRING"></a><a id="bidi_string"></a><dl>
<dt><b>BIDI_STRING</b></dt>
</dl>
</td>
<td width="60%">
Unicode character string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_TEXT"></a><a id="bidi_text"></a><dl>
<dt><b>BIDI_TEXT</b></dt>
</dl>
</td>
<td width="60%">
Non-localizable Unicode string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ENUM"></a><a id="bidi_enum"></a><dl>
<dt><b>BIDI_ENUM</b></dt>
</dl>
</td>
<td width="60%">
Enumeration data in the form of a Unicode string.

</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BLOB"></a><a id="bidi_blob"></a><dl>
<dt><b>BIDI_BLOB</b></dt>
</dl>
</td>
<td width="60%">
Binary data.

</td>
</tr>
</table>

`pData`

A pointer to the byte array that contains the data. For example, if <i>dwType</i> is BIDI_BOOL, <i>pData</i> points to a buffer that contains a Boolean value and if <i>dwType</i> is BIDI_BLOB, <i>pData</i> points to a buffer that contains the binary data.

`uSize`

Size, in bytes, of the byte array specified by <i>pData</i>.


## Return Value

The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The type of the data was not consistent with its size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Memory allocation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>

## Remarks

If an application calls <b>SetInputData</b> more than once, only the value of the last call will be set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Windows Server 2003 |
| **Target Platform** | Desktop |
| **Header** | bidispl.h |
| **Library** | bidispl.h |
| **DLL** | Bidispl.dll |

## See Also

<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="..\bidispl\nn-bidispl-ibidirequest.md">IBidiRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::SetInputData method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>