---
UID: NF:prcomoem.IPrintCorePS2.GetOptionAttribute
title: IPrintCorePS2::GetOptionAttribute method
author: windows-driver-content
description: The IPrintCorePS2::GetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
old-location: print\iprintcoreps2_getoptionattribute.htm
old-project: print
ms.assetid: b9ac4c2f-1eba-4425-a102-56fef6d0f5a7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetOptionAttribute method [Print Devices], GetOptionAttribute method [Print Devices], IPrintCorePS2 interface, GetOptionAttribute,IPrintCorePS2.GetOptionAttribute, IPrintCorePS2, IPrintCorePS2 interface [Print Devices], GetOptionAttribute method, IPrintCorePS2::GetOptionAttribute, prcomoem/IPrintCorePS2::GetOptionAttribute, print.iprintcoreps2_getoptionattribute, print_unidrv-pscript_rendering_514bd3e6-bf9e-464b-ade6-3a871523c9a4.xml
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
-	IPrintCorePS2.GetOptionAttribute
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# GetOptionAttribute method
The <code>IPrintCorePS2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.

## Syntax

````
HRESULT GetOptionAttribute(
  [in]  PDEVOBJ pdevobj,
  [in]  DWORD   dwFlags,
  [in]  PCSTR   pszFeatureKeyword,
  [in]  PCSTR   pszOptionKeyword,
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

Pointer to a caller-supplied buffer containing an ASCII string specifying the single feature keyword to query for.

`pszOptionKeyword`

Pointer to a caller-supplied buffer containing an ASCII string specifying the single option keyword to query for. This value can be obtained from a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552996">IPrintCorePS2::EnumOptions</a>.

`pszAttribute`

Pointer to a caller-supplied buffer containing an ASCII string specifying the single attribute requested. If this parameter is <b>NULL</b>, the caller is requesting a list of all supported attribute names for the option, as opposed to specifying a specific attribute name for the option.

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

The feature keyword name or option keyword name were not recognized.

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

If this method is called with its <i>pszAttribute</i> and <i>pbData</i> parameters set to <b>NULL</b>, the method returns with *<i>pcbNeeded</i> set to the number of bytes needed for the list of all supported attribute names for the option. If the method is called a second time, with <i>pszAttribute</i> set to <b>NULL</b> and <i>pbData</i> pointing to a buffer of the size specified in *<i>pcbNeeded</i> in the previous call, the method returns with *<i>pdwDataType</i> set to kADT_ASCII (an enumerator of the <a href="..\printoem\ne-printoem-_eattribute_datatype.md">EATTRIBUTE_DATATYPE</a> enumerated type) and <i>pbData</i> pointing to a null-delimited list of all the supported attribute names for the option. This list is terminated with two null characters.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/d35f0811-d572-422c-8672-ffd29bf69efa">Using GetOptionAttribute</a>.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553006">IPrintCorePS2::GetFeatureAttribute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552996">IPrintCorePS2::EnumOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::GetOptionAttribute method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>