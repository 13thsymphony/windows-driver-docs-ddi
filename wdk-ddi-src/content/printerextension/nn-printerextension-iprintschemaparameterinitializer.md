---
UID: NN:printerextension.IPrintSchemaParameterInitializer
title: IPrintSchemaParameterInitializer
author: windows-driver-content
description: The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification.
old-location: print\iprintschemaparameterinitializer.htm
old-project: print
ms.assetid: A4A1C231-3D71-4952-B5FA-0C8275DEF4F1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaParameterInitializer, IPrintSchemaParameterInitializer interface [Print Devices], IPrintSchemaParameterInitializer interface [Print Devices], described, print.iprintschemaparameterinitializer, printerextension/IPrintSchemaParameterInitializer
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
-	IPrintSchemaParameterInitializer
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaParameterInitializer interface

The <b>IPrintSchemaParameterInitializer</b> interface represents a parameter initialization value, as defined in the print schema specification.

For more information about the four data types that you can use with the &lt;psf:ParameterInit&gt; element, see section 2.1.3.2 of the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>.

## Methods

<p>The <b>IPrintSchemaParameterInitializer</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IPrintSchemaParameterInitializer::get_Value](nf-printerextension-iprintschemaparameterinitializer-get_value.md) | The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object. |
| [IPrintSchemaParameterInitializer::put_Value](nf-printerextension-iprintschemaparameterinitializer-put_value.md) | The Value (put_Value) property modifies the value of the IPrintSchemaParameterInitializer object. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>



<a href="https://msdn.microsoft.com/E5403359-A757-4530-B17B-C80E8A45AA92">IPrintSchematicket2::GetParameterInitializer</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/gg463385.aspx">Print Schema Specification</a>