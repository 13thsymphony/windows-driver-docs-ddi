---
UID: NF.filterpipeline.IPrintReadStream.Seek
title: IPrintReadStream::Seek method
author: windows-driver-content
description: The Seek method changes the seek pointer to a new location in the stream.
old-location: print\iprintreadstream_seek.htm
old-project: print
ms.assetid: b563e080-32ab-47b7-94f4-1d3dd19f3311
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintReadStream, IPrintReadStream::Seek, Seek
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintReadStream.Seek
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IPrintReadStream::Seek method



## -description
The <code>Seek</code> method changes the seek pointer to a new location in the stream.



## -syntax

````
HRESULT Seek(
  [in]  LONGLONG  dlibMove,
  [in]  DWORD     dwOrigin,
  [out] ULONGLONG *plibNewPosition
);
````


## -parameters

### -param dlibMove [in]

The displacement that is added to the location that <i>dwOrigin</i> specifies.


### -param dwOrigin [in]

The origin for the displacement that <i>dlibMove</i> specifies. The origin can be the beginning of the file (STREAM_SEEK_SET), the current seek pointer (STREAM_SEEK_CUR), or the end of the file (STREAM_SEEK_END). 


### -param plibNewPosition [out]

A pointer to the location where <code>Seek</code> writes the value of the new seek pointer from the beginning of the stream. 


## -returns
<code>Seek</code> returns an <b>HRESULT</b> value.


## -remarks
The <code>Seek</code> method might block, for example, if seeking to the end of the stream.

This method is similar to the <b>IStream::Seek</b> and <b>SetFilePointerEx</b> methods. For more information about these methods, see the Microsoft Windows SDK documentation.


## -requirements
<table>
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
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IDL

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>