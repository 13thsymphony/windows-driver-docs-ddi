---
UID: NF:prcomoem.IPrintCorePS2.GetFeatureAttribute
title: IPrintCorePS2::GetFeatureAttribute method
author: windows-driver-content
description: The IPrintCorePS2::GetFeatureAttribute method retrieves the feature attribute list or the value of a specific feature attribute.
old-location: print\iprintcoreps2_getfeatureattribute.htm
old-project: print
ms.assetid: 1a87da8a-a495-4451-a6f3-1261efda09f3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetFeatureAttribute method [Print Devices], GetFeatureAttribute method [Print Devices], IPrintCorePS2 interface, GetFeatureAttribute,IPrintCorePS2.GetFeatureAttribute, IPrintCorePS2, IPrintCorePS2 interface [Print Devices], GetFeatureAttribute method, IPrintCorePS2::GetFeatureAttribute, prcomoem/IPrintCorePS2::GetFeatureAttribute, print.iprintcoreps2_getfeatureattribute, print_unidrv-pscript_rendering_e3e316c3-10a4-429e-8a00-dfbd9034490e.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintCorePS2.GetFeatureAttribute
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# GetFeatureAttribute method
The <code>IPrintCorePS2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.

## Syntax

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

## Parameters

`pdevobj`

Pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.

`dwFlags`

Is reserved and must be set to zero.

`pszFeatureKeyword`

Pointer to a caller-supplied buffer containing an ASCII string specifying the single feature keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552990">IPrintCorePS2::EnumFeatures</a>.

`pszAttribute`

Pointer to a caller-supplied buffer containing an ASCII string specifying the single attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported feature attribute names, as opposed to specifying a specific feature attribute name.

`pdwDataType`

Pointer to a memory location that receives a value specifying the data type of the requested attribute. This value is an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumeration, which is defined in printoem.h.

`pbData`

Pointer to a caller-supplied buffer that receives the requested data. To simply query for the number of bytes needed to fulfill a request, set this parameter to <b>NULL</b>.

`cbSize`

Specifies the size, in bytes of the buffer pointed to by <i>pbData</i>.

`pcbNeeded`

Pointer to a memory location that receives the actual size, in bytes, of the requested data.


## Return Value

This method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pbData</i>).

The method was called with <i>pbData</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The method attempted to query for a nonexistent attribute.

The feature keyword was not recognized.

The <i>pdevobj</i> parameter pointed to an invalid driver context object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed.

</td>
</tr>
</table>

## Remarks

If this method is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbNeeded</i> set to the number of bytes needed for the list of all supported attribute names for the feature. If the method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size specified in *<i>pcbNeeded</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumerated type) and <i>pbData</i> pointing to a null-delimited list of all supported attribute names for the feature. This list is terminated with two null characters.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/e5050cb1-c178-405d-bb0e-fd7827198bca">Using GetFeatureAttribute</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |

## See Also

<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553009">IPrintCorePS2::GetGlobalAttribute</a>



<a href="..\prcomoem\nn-prcomoem-iprintcoreps2.md">IPrintCorePS2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553013">IPrintCorePS2::GetOptionAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552990">IPrintCorePS2::EnumFeatures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::GetFeatureAttribute method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>