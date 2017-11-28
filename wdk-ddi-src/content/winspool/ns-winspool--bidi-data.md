---
UID: NS.winspool._BIDI_DATA
title: BIDI_DATA
author: windows-driver-content
description: The BIDI_DATA structure is used to store the values of a bidi schema.
old-location: print\bidi_data.htm
old-project: print
ms.assetid: 9e0f3044-01c0-4dec-b34c-0f33ccfe3300
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: BIDI_DATA, BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA
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
req.alt-api: BIDI_DATA
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

# BIDI_DATA structure



## -description
<p>The BIDI_DATA structure is used to store the values of a bidi schema.</p>


## -syntax

````
typedef struct _BIDI_DATA {
  DWORD dwBidiType;
  union {
    BOOL             bData;
    LONG             iData;
    LPWSTR           sData;
    FLOAT            fData;
    BINARY_CONTAINER biData;
  } u;
} BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA;
````


## -struct-fields
<dl>

### -field <b>dwBidiType</b>

<dd>
<p>Specifies the type of data in a bidi request as one of the values listed in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545211">BIDI_TYPE</a> enumeration. The value of this member determines which one of the following five union members is valid.</p>
</dd>

### -field <b>u</b>

<dd>
<dl>

### -field <b>bData</b>

<dd>
<p>Specifies the Boolean value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BOOL, one of the BIDI_TYPE enumerators.</p>
</dd>

### -field <b>iData</b>

<dd>
<p>Specifies the integer value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_INT, one of the BIDI_TYPE enumerators.</p>
</dd>

### -field <b>sData</b>

<dd>
<p>Pointer to a memory location at which the first byte of the string is stored. This member is valid only if the value of <b>dwBidiType</b> is BIDI_STRING or BIDI_TEXT, two of the BIDI_TYPE enumerators.</p>
</dd>

### -field <b>fData</b>

<dd>
<p>Specifies the floating-point value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_FLOAT, one of the BIDI_TYPE enumerators.</p>
</dd>

### -field <b>biData</b>

<dd>
<p>Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545212">BINARY_CONTAINER</a> structure that holds the binary data. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BLOB, one of the BIDI_TYPE enumerators.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545196">BIDI_REQUEST_DATA</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545204">BIDI_RESPONSE_DATA</a> structures each have a member of this type, which holds the bidi data for the request or response.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545212">BINARY_CONTAINER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545211">BIDI_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545196">BIDI_REQUEST_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545204">BIDI_RESPONSE_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_DATA structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
