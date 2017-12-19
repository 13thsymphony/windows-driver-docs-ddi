---
UID: NF.prcomoem.IPrintCoreHelperPS.GetGlobalAttribute
title: IPrintCoreHelperPS::GetGlobalAttribute method
author: windows-driver-content
description: The IPrintCoreHelperPS::GetGlobalAttribute method retrieves the global attribute list or the value of a specific global attribute.
old-location: print\iprintcorehelperps_getglobalattribute.htm
old-project: print
ms.assetid: 4243ac31-83a7-47b5-8406-9d9537fbeb11
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS::GetGlobalAttribute, GetGlobalAttribute
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
req.alt-api: IPrintCoreHelperPS.GetGlobalAttribute
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
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::GetGlobalAttribute method



## -description
The <b>IPrintCoreHelperPS::GetGlobalAttribute</b> method retrieves the global attribute list or the value of a specific global attribute.



## -syntax

````
HRESULT GetGlobalAttribute(
  [in]  PCSTR  pszAttribute,
  [out] PDWORD pdwDataType,
  [out] PBYTE  pbData,
  [out] PDWORD pcbSize
);
````


## -parameters

### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the requested attribute. If this parameter is <b>NULL</b>, the caller is requesting a list of all of the supported global attribute names instead of specifying a specific global attribute name. 


### -param pdwDataType [out]

A pointer to variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the <a href="print.eattribute_datatype">EATTRIBUTE_DATATYPE</a> enumeration type, which is defined in printoem.h. 


### -param pbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.


### -param pcbSize [out]

A pointer to a variable that specifies the size, in bytes, of the buffer that is pointed to by the <i>pbData</i> parameter. 


## -returns
<b>IPrintCoreHelperPS::GetGlobalAttribute</b> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The method failed.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The method attempted to query for a nonexistent attribute.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The value in <i>pcbSize</i> was smaller than the number of bytes to be written to the output buffer that is pointed to by <i>pbData</i>.

 


## -remarks
If <b>IPrintCoreHelperPS::GetGlobalAttribute</b> is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbSize</i> set to the number of bytes that are needed for the list of all of the supported global attribute names. If this method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size that was specified in *<i>pcbSize</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="print.eattribute_datatype">EATTRIBUTE_DATATYPE</a> enumeration type) and <i>pbData</i> pointing to a NULL-delimited list of all of the supported global attribute names. This list is terminated with two null characters.

For more information about <b>IPrintCoreHelperPS::GetGlobalAttribute</b>, see <a href="https://msdn.microsoft.com/0e23ecba-7d89-44f5-b6a7-7d6be9a56765">Using GetGlobalAttribute</a>. 


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
<a href="print.iprintcorehelperps_getfeatureattribute">IPrintCoreHelperPS::GetFeatureAttribute</a>
</dt>
<dt>
<a href="print.iprintcorehelperps_getoptionattribute">IPrintCoreHelperPS::GetOptionAttribute</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::GetGlobalAttribute method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

