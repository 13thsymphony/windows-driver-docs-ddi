---
UID: NF.bidispl.IBidiRequest.GetOutputData
title: IBidiRequest::GetOutputData
author: windows-driver-content
description: The IBidiRequest::GetOutputData method gets the specified output data coming back from the printer.
old-location: print\ibidirequest_ibidirequest__getoutputdata.htm
old-project: print
ms.assetid: 0757dbc2-850b-4267-9339-b87591f85767
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IBidiRequest, GetOutputData, IBidiRequest::GetOutputData
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
req.alt-api: IBidiRequest.IBidiRequest::GetOutputData
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

# IBidiRequest::GetOutputData method



## -description
<p>The <b>IBidiRequest::GetOutputData</b> method gets the specified output data coming back from the printer.</p>


## -syntax

````
HRESULT IBidiRequest::GetOutputData(
  [in]  const DWORD  dwIndex,
  [out]       LPWSTR *ppszSchema,
  [out]       DWORD  *pdwType,
  [out]       BYTE   **ppData,
  [out]       ULONG  *uSize
);
````


## -parameters
<dl>

### -param <i>dwIndex</i> [in]

<dd>
<p>A zero-based index of the output data that is requested. For more information, see Remarks.</p>
</dd>

### -param <i>ppszSchema</i> [out]

<dd>
<p>A pointer to a NULL-terminated string that receives the schema string. The caller must call the <a href="_com_cotaskmemfree">CoTaskMemFree</a> function to free this pointer.</p>
</dd>

### -param <i>pdwType</i> [out]

<dd>
<p>A pointer to a variable that receives the type of the output data. This parameter can be one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="BIDI_NULL"></a><a id="bidi_null"></a><dl>

### -param <b>BIDI_NULL</b>

</dl>
</td>
<td width="60%">
<p>No data.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_INT"></a><a id="bidi_int"></a><dl>

### -param <b>BIDI_INT</b>

</dl>
</td>
<td width="60%">
<p>Integer data.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_FLOAT"></a><a id="bidi_float"></a><dl>

### -param <b>BIDI_FLOAT</b>

</dl>
</td>
<td width="60%">
<p>Floating-point number.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BOOL"></a><a id="bidi_bool"></a><dl>

### -param <b>BIDI_BOOL</b>

</dl>
</td>
<td width="60%">
<p><b>TRUE</b> or <b>FALSE</b>.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_STRING"></a><a id="bidi_string"></a><dl>

### -param <b>BIDI_STRING</b>

</dl>
</td>
<td width="60%">
<p>Unicode character string.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_TEXT"></a><a id="bidi_text"></a><dl>

### -param <b>BIDI_TEXT</b>

</dl>
</td>
<td width="60%">
<p>Non-localizable Unicode string.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_ENUM"></a><a id="bidi_enum"></a><dl>

### -param <b>BIDI_ENUM</b>

</dl>
</td>
<td width="60%">
<p>Enumeration data in the form of a Unicode string.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="BIDI_BLOB"></a><a id="bidi_blob"></a><dl>

### -param <b>BIDI_BLOB</b>

</dl>
</td>
<td width="60%">
<p>Binary data.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>ppData</i> [out]

<dd>
<p>A pointer to the variable that receives a pointer to the byte array containing the output data. The buffer is allocated by the COM interface to store the output data. The caller is responsible for calling <a href="_com_cotaskmemfree">CoTaskMemFree</a> to free the buffer.</p>
</dd>

### -param <i>uSize</i> [out]

<dd>
<p>A pointer to a variable that receives the size of the byte array specified by **ppData.</p>
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

## -remarks
<p>A single bidi request can have multiple results. The application calls <a href="https://msdn.microsoft.com/library/windows/hardware/dd144974">IBidiRequest::GetEnumCount</a> to get the number of results from the bidi request.</p>

<p>If an application calls <b>GetOutputData</b> with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.</p>

<p>A single bidi request can have multiple results. The application calls <a href="https://msdn.microsoft.com/library/windows/hardware/dd144974">IBidiRequest::GetEnumCount</a> to get the number of results from the bidi request.</p>

<p>If an application calls <b>GetOutputData</b> with the same index twice, the interface allocates two different buffers and thus the application must free both buffers.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="NULL">Bidirectional Communication Schema</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dd144969">IBidiRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dd144974">IBidiRequest::GetEnumCount</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest::IBidiRequest::GetOutputData method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
