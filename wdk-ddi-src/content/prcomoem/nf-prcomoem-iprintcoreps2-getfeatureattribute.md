---
UID: NF:prcomoem.IPrintCorePS2.GetFeatureAttribute
title: IPrintCorePS2::GetFeatureAttribute method
author: windows-driver-content
description: The IPrintCorePS2::GetFeatureAttribute method retrieves the feature attribute list or the value of a specific feature attribute.
old-location: print\iprintcoreps2_getfeatureattribute.htm
old-project: print
ms.assetid: 1a87da8a-a495-4451-a6f3-1261efda09f3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCorePS2, IPrintCorePS2::GetFeatureAttribute, GetFeatureAttribute
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
req.alt-api: IPrintCorePS2.GetFeatureAttribute
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

# IPrintCorePS2::GetFeatureAttribute method



## -description
The <code>IPrintCorePS2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.



## -syntax

````
HRESULT GetFeatureAttribute(
  [in]  PDEVOBJ pdevobj,
  [in]  DWORD   dwFlags,
  [in]  PCSTR   pszFeatureKeyword,
  [in]  PCSTR   pszAttribute,
  [out] PDWORD  pdwDataType,
  [out] PBYTE   pbData,
  [in]  DWORD   cbSize,
  [out] PDWORD  pcbNeeded
);
````


## -parameters

### -param pdevobj [in]

Pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pszFeatureKeyword [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying the single feature keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552990">IPrintCorePS2::EnumFeatures</a>.


### -param pszAttribute [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying the single attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported feature attribute names, as opposed to specifying a specific feature attribute name.


### -param pdwDataType [out]

Pointer to a memory location that receives a value specifying the data type of the requested attribute. This value is an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration, which is defined in printoem.h.


### -param pbData [out]

Pointer to a caller-supplied buffer that receives the requested data. To simply query for the number of bytes needed to fulfill a request, set this parameter to <b>NULL</b>.


### -param cbSize [in]

Specifies the size, in bytes of the buffer pointed to by <i>pbData</i>.


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the requested data.


## -returns
This method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pbData</i>).

The method was called with <i>pbData</i> set to <b>NULL</b>.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The method attempted to query for a nonexistent attribute.

The feature keyword was not recognized.

The <i>pdevobj</i> parameter pointed to an invalid driver context object.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The method failed.

 


## -remarks
If this method is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbNeeded</i> set to the number of bytes needed for the list of all supported attribute names for the feature. If the method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size specified in *<i>pcbNeeded</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumerated type) and <i>pbData</i> pointing to a null-delimited list of all supported attribute names for the feature. This list is terminated with two null characters.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/e5050cb1-c178-405d-bb0e-fd7827198bca">Using GetFeatureAttribute</a>.


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
<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552990">IPrintCorePS2::EnumFeatures</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553009">IPrintCorePS2::GetGlobalAttribute</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553013">IPrintCorePS2::GetOptionAttribute</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::GetFeatureAttribute method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

