---
UID: NF.wiamdef.WIAS_LHRESULT
title: WIAS_LHRESULT macro
author: windows-driver-content
description: The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the WIAS_HRESULT macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.
old-location: image\wias_lhresult.htm
old-project: Image
ms.assetid: dcc02735-632f-4b86-ac4f-833c8dcba1c5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WIAS_LHRESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later. Use WIAS_HRESULT instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_LHRESULT
req.alt-loc: wiamdef.h
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
req.product: Windows 10 or later.
---

# WIAS_LHRESULT macro



## -description
The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the <a href="image.wias_hresult">WIAS_HRESULT</a> macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.



## -syntax

````
VOID WIAS_LHRESULT(
   IWiaLog *pIWiaLog,
   HRESULT hr
);
````


## -parameters

### -param pIWiaLog 

Pointer to an <a href="image.iwialog_interface">IWiaLog Interface</a>.


### -param hr 

Specifies the HRESULT value to be translated into a string.


## -remarks
The following is an example of how the macro can be used:

The WIAS_LHRESULT macro is not recommended for Windows Vista and later operating system versions. It is recommended that the <a href="image.wias_hresult">WIAS_HRESULT</a> macro be used instead. 


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
Version

</th>
<td width="70%">
Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later. Use WIAS_HRESULT instead.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.wias_lerror">WIAS_LERROR</a>
</dt>
<dt>
<a href="image.wias_ltrace">WIAS_LTRACE</a>
</dt>
<dt>
<a href="image.wias_lwarning">WIAS_LWARNING</a>
</dt>
<dt>
<a href="image.wias_hresult">WIAS_HRESULT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_LHRESULT macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

