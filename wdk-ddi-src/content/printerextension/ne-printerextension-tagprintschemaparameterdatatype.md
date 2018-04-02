---
UID: NE:printerextension.tagPrintSchemaParameterDataType
title: tagPrintSchemaParameterDataType
author: windows-driver-content
description: The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.
old-location: print\tagprintschemaparameterdatatype.htm
old-project: print
ms.assetid: 3276C273-C950-4DC9-B338-E6E7E30DEB77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PrintSchemaParameterDataType, PrintSchemaParameterDataType enumeration [Print Devices], PrintSchemaParameterDataType_Integer, PrintSchemaParameterDataType_NumericString, PrintSchemaParameterDataType_String, print.tagprintschemaparameterdatatype, printerextension/PrintSchemaParameterDataType, printerextension/PrintSchemaParameterDataType_Integer, printerextension/PrintSchemaParameterDataType_NumericString, printerextension/PrintSchemaParameterDataType_String, tagPrintSchemaParameterDataType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Printerextension.h
api_name:
-	PrintSchemaParameterDataType
product: Windows
targetos: Windows
req.typenames: PrintSchemaParameterDataType
req.product: Windows 10 or later.
---

# tagPrintSchemaParameterDataType Enumeration
The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.

## Syntax
```
typedef enum tagPrintSchemaParameterDataType {
  PrintSchemaParameterDataType_Integer        ,
  PrintSchemaParameterDataType_NumericString  ,
  PrintSchemaParameterDataType_String
} PrintSchemaParameterDataType;
```

## Constants

<table>
            
                <tr>
                    <td>PrintSchemaParameterDataType_Integer</td>
                    <td>Integer data type.
This maps to the Print Schema’s IntegerParamType parameters.</td>
                </tr>
            
                <tr>
                    <td>PrintSchemaParameterDataType_NumericString</td>
                    <td>String data type with only numeric chars allowed.
This maps to the Print Schema’s StringParamType parameters, with UnitType = “numeric”.</td>
                </tr>
            
                <tr>
                    <td>PrintSchemaParameterDataType_String</td>
                    <td>String data type with arbitrary chars allowed.
This maps to the Print Schema’s StringParamType parameters, with UnitType not equal to “numeric”.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/82CC79A8-0281-4100-B3FB-1FFFB2454B8D">IPrintSchemaParameterDefinition::DataType</a>