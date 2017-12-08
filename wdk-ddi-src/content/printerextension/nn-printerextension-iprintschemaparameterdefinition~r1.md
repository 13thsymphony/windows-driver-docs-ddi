---
UID: NN.printerextension.IPrintSchemaParameterDefinition~r1
title: IPrintSchemaParameterDefinition
author: windows-driver-content
description: The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification.
old-location: print\iprintschemaparameterdefinition.htm
old-project: print
ms.assetid: 205A4F09-6FE5-459E-A94A-13B1839AF489
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: tagPrintSchemaSelectionType, PrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaParameterDefinition
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IPrintSchemaParameterDefinition interface



## -description
The <b>IPrintSchemaParameterDefinition</b> interface represents a parameter definition, as defined in the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>. 
For more information about the four data types that you can use with the &lt;psf:ParameterDef&gt; element, see section 2.1.3.1 of the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaParameterDefinition</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprintschemadisplayableelement.md">IPrintSchemaDisplayableElement</a>. <b>IPrintSchemaParameterDefinition</b> also has these types of members:

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaParameterDefinition</b> interface has these properties.


<a href="print._iprintschemaparameterdefinition_datatype">DataType</a>


Read-only

The <b>DataType</b> property Gets the <a href="print.tagprintschemaparameterdatatype">PrintSchemaParameterDataType</a> enumerated value that indicates the expected data type for the Print Schema parameter.


<a href="print._iprintschemaparameterdefinition_rangemax">RangeMax</a>


Read-only

The <b>RangeMax</b> property Gets the maximum value of the allowed data range.


<a href="print._iprintschemaparameterdefinition_rangemin">RangeMin</a>


Read-only

The <b>RangeMin</b> property Gets the minimum value of the allowed data range.


<a href="print._iprintschemaparameterdefinition_unittype">UnitType</a>


Read-only

The <b>UnitType</b> property Gets the unit type.


<a href="print._iprintschemaparameterdefinition_userinputrequired">UserInputRequired</a>


Read-only

The <b>UserInputRequired</b> property Gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemadisplayableelement.md">IPrintSchemaDisplayableElement</a>
</dt>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a></dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaParameterDefinition interface%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
