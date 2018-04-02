---
UID: NC:printoem.PFNGETINFO
title: PFNGETINFO
author: windows-driver-content
description: The UNIFONTOBJ_GetInfo callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.
old-location: print\unifontobj_getinfo.htm
old-project: print
ms.assetid: 2c0d350d-dcdf-4da7-8cca-7f36d4ca622e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFNGETINFO, UNIFONTOBJ_GetInfo, UNIFONTOBJ_GetInfo routine [Print Devices], print.unifontobj_getinfo, print_unidrv-pscript_rendering_7dc55246-beaa-4058-87a3-5438db3368c4.xml, printoem/UNIFONTOBJ_GetInfo
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	printoem.h
api_name:
-	UNIFONTOBJ_GetInfo
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# PFNGETINFO callback function
The <b>UNIFONTOBJ_GetInfo</b> callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information.

## Syntax

```
PFNGETINFO Pfngetinfo;

BOOL Pfngetinfo(
  _UNIFONTOBJ *,
   DWORD,
   PVOID,
   DWORD,
   PDWORD
)
{...}
```

## Parameters

`*`



`DWORD`



`PVOID`



`DWORD`



`PDWORD`




## Return Value

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise it returns <b>FALSE</b>.

## Remarks

The <b>UNIFONTOBJ_GetInfo</b> callback function allows a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> to call back into Unidrv to obtain font or glyph information from GDI, needed for handling <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">customized font management</a> operations.

A rendering plug-in receives the <b>UNIFONTOBJ_GetInfo</b> function's address in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563590">UNIFONTOBJ</a> structure that is passed to the font customization methods.

The type of information returned by the function is dependent on the input arguments. The caller supplies values for <i>dwInfoID</i>, <i>pData</i>, and <i>dwDataSize</i> to indicate the type of information wanted. The following table summarizes the types of information returned. For more information, see the structure descriptions.

<table>
<tr>
<th><i>pData</i> Structure</th>
<th>Returned Information</th>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549929">GETINFO_FONTOBJ</a>


</td>
<td>
A FONTOBJ structure describing the current font.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549934">GETINFO_GLYPHBITMAP</a>


</td>
<td>
A single glyph bitmap.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550436">GETINFO_GLYPHSTRING</a>


</td>
<td>
An array of glyph specifiers in a specified format.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550439">GETINFO_GLYPHWIDTH</a>


</td>
<td>
Total width of a set of glyphs.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550446">GETINFO_MEMORY</a>


</td>
<td>
Amount of available printer memory remaining.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550451">GETINFO_STDVAR</a>


</td>
<td>
The current value for one or more of Unidrv's <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>.

</td>
</tr>
</table>
 

If the buffer described by <i>pData</i> and <i>dwDataSize</i> is too small to receive the structure indicated by <i>dwInfoID</i>, the function loads the required buffer size into the location pointed by <i>pcbNeeded</i> and returns <b>FALSE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printoem.h (include Printoem.h) |