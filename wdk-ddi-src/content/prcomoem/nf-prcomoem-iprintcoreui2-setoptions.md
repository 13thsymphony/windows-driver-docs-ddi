---
UID: NF:prcomoem.IPrintCoreUI2.SetOptions
title: IPrintCoreUI2::SetOptions method
author: windows-driver-content
description: The IPrintCoreUI2::SetOptions method sets the driver's feature settings.
old-location: print\iprintcoreui2_setoptions.htm
old-project: print
ms.assetid: b608e331-6b13-4b27-8bb1-00a7c2fef281
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreUI2, IPrintCoreUI2::SetOptions, SetOptions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreUI2.SetOptions
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreUI2::SetOptions method



## -description
The <code>IPrintCoreUI2::SetOptions</code> method sets the driver's feature settings.



## -syntax

````
HRESULT SetOptions(
  [in]  POEMUIOBJ poemuiobj,
  [in]  DWORD     dwFlags,
  [in]  PCSTR     pmszFeatureOptionBuf,
  [in]  DWORD     cbIn,
  [out] PDWORD    pdwResult
);
````


## -parameters

### -param poemuiobj [in]

Pointer to the current context, an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure.


### -param dwFlags [in]

Specifies whether the core driver is to resolve conflicts. This parameter must be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SETOPTIONS_FLAG_KEEP_CONFLICT

</td>
<td>
Ask core driver to not resolve any conflict that arises.

</td>
</tr>
<tr>
<td>
SETOPTIONS_FLAG_RESOLVE_CONFLICT

</td>
<td>
Ask core driver to resolve any conflict that arises.

</td>
</tr>
</table>
 


### -param pmszFeatureOptionBuf [in]

Pointer to a caller-supplied buffer containing a list of feature/option keyword pairs in MULTI_SZ format. Each item in this list is separated from the next by a null character, and the list is terminated with two null characters.


### -param cbIn [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureOptionBuf</i>. This size includes the last MULTI_SZ null character.


### -param pdwResult [out]

Pointer to a memory location that receives one of the following values. These constants are defined in printoem.h.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_CONFLICT_REMAINED

</td>
<td>
The core driver found conflicts, but has left them unresolved.

</td>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_CONFLICT_RESOLVED

</td>
<td>
The core driver found and resolved all conflicts.

</td>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_NO_CONFLICT

</td>
<td>
The core driver did not find any conflict.

</td>
</tr>
</table>
 


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not supported.

A structure of the type specified by <i>dwLevel</i> is not supported.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The value in <i>dwFlags</i> was incorrect.

The input buffer (pointed to by <i>pmszFeatureOptionBuf</i>) was not in MULTI_SZ format.

The <i>poemuiobj</i> parameter pointed to an invalid context object.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The method failed

 


## -remarks
This method is supported only for Windows XP Pscript5 plug-ins, not for Unidrv plug-ins.

This method is called to set the driver's feature settings using a list of feature/option keyword pairs. The caller can access the resultant feature settings using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553069">IPrintCoreUI2::GetOptions</a> method. 

If this method returns any value other than S_OK, then it did not make any change in the driver's feature settings.

The <i>pmszFeatureOptionBuf</i> input buffer must be constructed in the same way as the output buffer of the <b>IPrintCoreUI2::GetOptions</b> method. That is, the feature/option keyword pairs must be in MULTI_SZ format, and each item in the list is separated from the next by a null character. A pair of null characters terminates the list.

If the input buffer contains a feature keyword or its option keyword that is not recognized, or the feature is recognized but not supported in the current sticky mode (see <a href="https://msdn.microsoft.com/b7f79841-f82c-4a60-9c2f-58772a65a5eb">Replacing Driver-Supplied Property Sheet Pages</a>), then the feature/option pair is ignored, and the current option for that feature continues to be in effect.

This method is supported only for UI plug-ins that fully replace the core driver's standard UI pages, and is supported only during the UI plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines.

For more information, see <a href="https://msdn.microsoft.com/c8b5c235-0b74-47c8-b6ba-eba810a8467b">Using GetOptions and SetOptions</a>.


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
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553069">IPrintCoreUI2::GetOptions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::SetOptions method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

