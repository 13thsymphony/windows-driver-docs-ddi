---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_RangeMin
title: IPrintSchemaParameterDefinition::get_RangeMin method
author: windows-driver-content
description: The RangeMin property gets the minimum value of the allowed data range.
old-location: print\_iprintschemaparameterdefinition_rangemin.htm
old-project: print
ms.assetid: ED8A29D9-84CE-4FB5-BCEE-C31DA9AB3D00
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaParameterDefinition, IPrintSchemaParameterDefinition interface [Print Devices], RangeMin property, IPrintSchemaParameterDefinition.RangeMin, IPrintSchemaParameterDefinition::get_RangeMin, RangeMin property [Print Devices], RangeMin property [Print Devices], IPrintSchemaParameterDefinition interface, get_RangeMin, get_RangeMin,IPrintSchemaParameterDefinition.get_RangeMin, print._iprintschemaparameterdefinition_rangemin, printerextension/IPrintSchemaParameterDefinition::RangeMin, printerextension/IPrintSchemaParameterDefinition::get_RangeMin
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
-	IPrintSchemaParameterDefinition.RangeMin
-	IPrintSchemaParameterDefinition.get_RangeMin
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_RangeMin method
The <b>RangeMin</b> property gets the minimum value of the allowed data range.

This property is read-only.

## Syntax

````
HRESULT get_RangeMin(
  [out, retval] INT *pRangeMin
);
````

## Parameters

`pRangeMin`




## Return Value

None

## Remarks

For the <b>PrintSchemaParameterDataType_Integer</b> data type, the value returned by  <b>RangeMin</b> maps to the &lt;psf:MinValue&gt; property value of the Print Schema parameter definition. This minimum value shows the minimum integer value that the driver supports.

For the <b>PrintSchemaParameterDataType_NumericString</b> and <b>PrintSchemaParameterDataType_String</b>  data types, this maps to the &lt;psf:MinLength&gt; property value of the Print Schema parameter definition. This minimum value shows the minimum length of string that the driver supports.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md">IPrintSchemaParameterDefinition</a>