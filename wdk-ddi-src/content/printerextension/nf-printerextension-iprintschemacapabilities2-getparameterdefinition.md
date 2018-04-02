---
UID: NF:printerextension.IPrintSchemaCapabilities2.GetParameterDefinition
title: IPrintSchemaCapabilities2::GetParameterDefinition method
author: windows-driver-content
description: The GetParameterDefinition method retrieves the IPrintSchemaParameterDefinition object, and it represents the &lt;psf:ParameterDef&gt; element in the PrintCapabilites XML.
old-location: print\iprintschemacapabilities2_getparameterdefinition.htm
old-project: print
ms.assetid: 19C3A3C5-446B-48FD-8E77-2E0F787B16B1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetParameterDefinition method [Print Devices], GetParameterDefinition method [Print Devices], IPrintSchemaCapabilities2 interface, GetParameterDefinition,IPrintSchemaCapabilities2.GetParameterDefinition, IPrintSchemaCapabilities2, IPrintSchemaCapabilities2 interface [Print Devices], GetParameterDefinition method, IPrintSchemaCapabilities2::GetParameterDefinition, print.iprintschemacapabilities2_getparameterdefinition, printerextension/IPrintSchemaCapabilities2::GetParameterDefinition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaCapabilities2.GetParameterDefinition
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaCapabilities2::GetParameterDefinition method
The <b>GetParameterDefinition</b> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a> object, and it  represents the &lt;psf:ParameterDef&gt; element in the PrintCapabilites XML.

 The keyword name and keyword namespace URI specify the <b>IPrintSchemaParameterDefinition</b> object to be retrieved.

## Syntax

```
HRESULT GetParameterDefinition(
  BSTR                            bstrName,
  BSTR                            bstrNamespaceUri,
  IPrintSchemaParameterDefinition **ppParameterDefinition
);
```

## Parameters

`bstrName`

The keyword name.

`bstrNamespaceUri`

The keyword namespace URI.

`ppParameterDefinition`

The <b>IPrintSchemaParameterDefinition</b> object.


## Return Value

The <b>GetParameterDefinition</b> method returns an <b>HRESULT</b> value. If the property call was not successful, it returns the appropriate <b>HRESULT</b> error code.

## Remarks

To be consistent with <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>, the <b>GetParameterDefinition</b> method works for any &lt;psf:ParameterDef&gt; element that is defined in the public keyword namespaces.  The <b>GetParameterDefinition</b> method also works for any IHV-defined  private keyword namespace that uses  either the StringParamType or the IntegerParamType data type.

When you use the &lt;psf:ParameterDef&gt; element with the QNameParamType or the DecimalParamType data type, <b>GetParameterDefinition</b> will return HRESULT_FROM_WIN32 (ERROR_NOT_SUPPORTED).

For more information about the data types that you can use with the &lt;psf:ParameterDef&gt; element, see section 2.1.3.1 of the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn465887">IPrintSchemaCapabilities2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>