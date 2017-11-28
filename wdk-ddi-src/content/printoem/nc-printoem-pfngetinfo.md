---
UID: NC.printoem.PFNGETINFO
title: PFNGETINFO
author: windows-driver-content
description: The UNIFONTOBJ_GetInfo callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.
old-location: print\unifontobj_getinfo.htm
old-project: print
ms.assetid: 2c0d350d-dcdf-4da7-8cca-7f36d4ca622e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintSchemaTicket2, GetParameterInitializer, IPrintSchemaTicket2::GetParameterInitializer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UNIFONTOBJ_GetInfo
req.alt-loc: printoem.h
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
req.iface: IPrintSchemaTicket2
req.product: Windows 10 or later.
---

# PFNGETINFO callback



## -description
<p>The <b>UNIFONTOBJ_GetInfo</b> callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.</p>


## -prototype

````
PFNGETINFO UNIFONTOBJ_GetInfo;

BOOL APIENTRY UNIFONTOBJ_GetInfo(
   struct _UNIFONTOBJ *pUFObj,
   DWORD              dwInfoID,
   PVOID              pData,
   DWORD              dwDataSize,
   PDWORD             pcbNeeded
)
{ ... }
````


## -parameters
<dl>

### -param <i>pUFObj</i> 

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563590">UNIFONTOBJ</a> structure received by the function that is making the callback to <b>UNIFONTOBJ_GetInfo</b>. Supplied by the caller.</p>
</dd>

### -param <i>dwInfoID</i> 

<dd>
<p>Specifies the type of structure pointed to by <i>pData</i>. Supplied by the caller. See the following table.</p>
</dd>

### -param <i>pData</i> 

<dd>
<p>Pointer to a structure, as indicated in the following table. Supplied by the caller.</p>
<table>
<tr>
<th>dwInfoID Value</th>
<th><i>pData</i> Structure</th>
</tr>
<tr>
<td>
<p>UFO_GETINFO_FONTOBJ</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549929">GETINFO_FONTOBJ</a>
</p>
</td>
</tr>
<tr>
<td>
<p>UFO_GETINFO_GLYPHBITMAP</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549934">GETINFO_GLYPHBITMAP</a>
</p>
</td>
</tr>
<tr>
<td>
<p>UFO_GETINFO_GLYPHSTRING</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550436">GETINFO_GLYPHSTRING</a>
</p>
</td>
</tr>
<tr>
<td>
<p>UFO_GETINFO_GLYPHWIDTH</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550439">GETINFO_GLYPHWIDTH</a>
</p>
</td>
</tr>
<tr>
<td>
<p>UFO_GETINFO_MEMORY</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550446">GETINFO_MEMORY</a>
</p>
</td>
</tr>
<tr>
<td>
<p>UFO_GETINFO_STDVARIABLE</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550451">GETINFO_STDVAR</a>
</p>
</td>
</tr>
</table>
<p> </p>
<dl>
<dd>
<p>For a summary of structure contents, see the following <b>Remarks</b> section.</p>
</dd>
</dl>
</dd>

### -param <i>dwDataSize</i> 

<dd>
<p>Specifies the size, in bytes, of the buffer pointed to by <i>pData</i>. Supplied by the caller.</p>
</dd>

### -param <i>pcbNeeded</i> 

<dd>
<p>Pointer to a location that receives the minimum buffer size, in bytes, required to contain the structure identified by <i>dwInfoID</i>. Supplied by the caller.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function returns <b>TRUE</b>. Otherwise it returns <b>FALSE</b>.</p>

## -remarks
<p>The <b>UNIFONTOBJ_GetInfo</b> callback function allows a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> to call back into Unidrv to obtain font or glyph information from GDI, needed for handling <a href="NULL">customized font management</a> operations.</p>

<p>A rendering plug-in receives the <b>UNIFONTOBJ_GetInfo</b> function's address in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563590">UNIFONTOBJ</a> structure that is passed to the font customization methods.</p>

<p>The type of information returned by the function is dependent on the input arguments. The caller supplies values for <i>dwInfoID</i>, <i>pData</i>, and <i>dwDataSize</i> to indicate the type of information wanted. The following table summarizes the types of information returned. For more information, see the structure descriptions.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549929">GETINFO_FONTOBJ</a>
</p>

<p>A FONTOBJ structure describing the current font.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549934">GETINFO_GLYPHBITMAP</a>
</p>

<p>A single glyph bitmap.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550436">GETINFO_GLYPHSTRING</a>
</p>

<p>An array of glyph specifiers in a specified format.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550439">GETINFO_GLYPHWIDTH</a>
</p>

<p>Total width of a set of glyphs.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550446">GETINFO_MEMORY</a>
</p>

<p>Amount of available printer memory remaining.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550451">GETINFO_STDVAR</a>
</p>

<p>The current value for one or more of Unidrv's <a href="NULL">standard variables</a>.</p>

<p> </p>

<p>If the buffer described by <i>pData</i> and <i>dwDataSize</i> is too small to receive the structure indicated by <i>dwInfoID</i>, the function loads the required buffer size into the location pointed by <i>pcbNeeded</i> and returns <b>FALSE</b>.</p>

<p>The <b>UNIFONTOBJ_GetInfo</b> callback function allows a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> to call back into Unidrv to obtain font or glyph information from GDI, needed for handling <a href="NULL">customized font management</a> operations.</p>

<p>A rendering plug-in receives the <b>UNIFONTOBJ_GetInfo</b> function's address in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563590">UNIFONTOBJ</a> structure that is passed to the font customization methods.</p>

<p>The type of information returned by the function is dependent on the input arguments. The caller supplies values for <i>dwInfoID</i>, <i>pData</i>, and <i>dwDataSize</i> to indicate the type of information wanted. The following table summarizes the types of information returned. For more information, see the structure descriptions.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549929">GETINFO_FONTOBJ</a>
</p>

<p>A FONTOBJ structure describing the current font.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549934">GETINFO_GLYPHBITMAP</a>
</p>

<p>A single glyph bitmap.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550436">GETINFO_GLYPHSTRING</a>
</p>

<p>An array of glyph specifiers in a specified format.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550439">GETINFO_GLYPHWIDTH</a>
</p>

<p>Total width of a set of glyphs.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550446">GETINFO_MEMORY</a>
</p>

<p>Amount of available printer memory remaining.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550451">GETINFO_STDVAR</a>
</p>

<p>The current value for one or more of Unidrv's <a href="NULL">standard variables</a>.</p>

<p> </p>

<p>If the buffer described by <i>pData</i> and <i>dwDataSize</i> is too small to receive the structure indicated by <i>dwInfoID</i>, the function loads the required buffer size into the location pointed by <i>pcbNeeded</i> and returns <b>FALSE</b>.</p>

## -requirements
<table>
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
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>