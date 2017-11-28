---
UID: NF.prcomoem.IPrintCoreHelperPS.GetOptionAttribute
title: IPrintCoreHelperPS::GetOptionAttribute
author: windows-driver-content
description: The IPrintCoreHelperPS::GetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
old-location: print\iprintcorehelperps_getoptionattribute.htm
old-project: print
ms.assetid: 66e794e6-ded0-41b1-b52b-d886bb58a4ff
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintCoreHelperPS, GetOptionAttribute, IPrintCoreHelperPS::GetOptionAttribute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreHelperPS.GetOptionAttribute
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
req.iface: IPrintCoreHelperPS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::GetOptionAttribute method



## -description
<p>The <b>IPrintCoreHelperPS::GetOptionAttribute</b> method retrieves the option attribute list or the value of a specific option attribute.</p>


## -syntax

````
HRESULT GetOptionAttribute(
  [in]  PCSTR  pszFeatureKeyword,
  [in]  PCSTR  pszOptionKeyword,
  [in]  PCSTR  pszAttribute,
  [out] PDWORD pdwDataType,
  [out] PBYTE  *pbData,
  [out] PDWORD pcbSize
);
````


## -parameters
<dl>

### -param <i>pszFeatureKeyword</i> [in]

<dd>
<p>A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for. </p>
</dd>

### -param <i>pszOptionKeyword</i> [in]

<dd>
<p>A pointer to a caller-supplied buffer that contains an ANSI string that specifies the option keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551987">IPrintCoreHelperPS::EnumOptions</a>.</p>
</dd>

### -param <i>pszAttribute</i> [in]

<dd>
<p>A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported attribute names for the option instead of specifying a specific attribute name for the option.</p>
</dd>

### -param <i>pdwDataType</i> [out]

<dd>
<p>A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h.</p>
</dd>

### -param <i>pbData</i> [out]

<dd>
<p>A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.</p>
</dd>

### -param <i>pcbSize</i> [out]

<dd>
<p>A pointer to a variable that receives the size, in bytes, of the buffer that is pointed to by the <i>pbData</i> parameter.</p>
</dd>
</dl>

## -returns
<p><b>IPrintCoreHelperPS::GetOptionAttribute</b> should return one of the following values.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method succeeded.</p><dl>
<dt><b>E_FAIL</b></dt>
</dl><p>The method failed.</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>The method attempted to query for a nonexistent attribute.</p>

<p>This value might also mean that the feature keyword name or option keyword name were not recognized.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>The value in <i>pcbSize</i> was smaller than the number of bytes to be written to the output buffer that is pointed to by <i>pbData</i>.</p>

<p> </p>

## -remarks
<p>If <b>IPrintCoreHelperPS::GetOptionAttribute </b>is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported attribute names for the option. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported attribute names for the option. This list is terminated with two null characters.</p>

<p>For more information about <b>IPrintCoreHelperPS::GetOptionAttribute</b>, see <a href="NULL">Using GetOptionAttribute</a>.</p>

<p>If <b>IPrintCoreHelperPS::GetOptionAttribute </b>is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported attribute names for the option. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548692">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported attribute names for the option. This list is terminated with two null characters.</p>

<p>For more information about <b>IPrintCoreHelperPS::GetOptionAttribute</b>, see <a href="NULL">Using GetOptionAttribute</a>.</p>

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
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551998">IPrintCoreHelperPS::GetFeatureAttribute</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552899">IPrintCoreHelperPS::GetGlobalAttribute</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::GetOptionAttribute method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
