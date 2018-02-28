---
UID: NF:printerextension.IPrintSchemaParameterInitializer.put_Value
title: IPrintSchemaParameterInitializer::put_Value method
author: windows-driver-content
description: The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object.
old-location: print\iprintschemaparameterinitializer_getvalue.htm
old-project: print
ms.assetid: CDBAB58C-F051-4047-A538-5504F0E28EC7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintSchemaParameterInitializer, IPrintSchemaParameterInitializer interface [Print Devices], Value property, IPrintSchemaParameterInitializer,get_Value, IPrintSchemaParameterInitializer.Value, IPrintSchemaParameterInitializer::get_Value, IPrintSchemaParameterInitializer::put_Value, Value property [Print Devices], Value property [Print Devices], IPrintSchemaParameterInitializer interface, print.iprintschemaparameterinitializer_getvalue, printerextension/IPrintSchemaParameterInitializer::Value, printerextension/IPrintSchemaParameterInitializer::get_Value, put_Value,IPrintSchemaParameterInitializer.put_Value
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaParameterInitializer.Value
-	IPrintSchemaParameterInitializer.get_Value
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# put_Value method
The <b>Value</b> (get_Value) property gets the current value of the <a href="..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md">IPrintSchemaParameterInitializer</a> object.

 In PrintTicket XML, that’s the value of the &lt;psf:Value&gt; child element for the &lt;psf:ParameterInit&gt; element.

This property is read-only.

## Syntax

````
HRESULT get_Value(
  [out, retval] VARIANT *pVar
);
````

## Parameters

`pVar`




## Return Value

None

## Remarks

The <b>Value</b> (get_Value) property returns the current value of the <b>IPrintSchemaParameterInitializer</b> object in the form of a Variant variable. Here's how the value and type are stored in the Variant for the different parameter data types:

<table>
<tr>
<th>Parameter DataType</th>
<th>Variant type</th>
<th>Variant value</th>
</tr>
<tr>
<td>PrintSchemaParameterDataType_Integer</td>
<td>V_VT(pVar) is VT_I4</td>
<td>V_I4(pVar)</td>
</tr>
<tr>
<td>PrintSchemaParameterDataType_NumericString</td>
<td>V_VT(pVar) is VT_BSTR</td>
<td>V_BSTR(pVar)</td>
</tr>
<tr>
<td>PrintSchemaParameterDataType_String</td>
<td>V_VT(pVar) is VT_BSTR</td>
<td>V_BSTR(pVar)</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md">IPrintSchemaParameterInitializer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaParameterInitializer::Value property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>