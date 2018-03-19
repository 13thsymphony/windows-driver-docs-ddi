---
UID: NE:pep_x._PEP_ACPI_OBJECT_TYPE
title: "_PEP_ACPI_OBJECT_TYPE"
author: windows-driver-content
description: The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object.
old-location: kernel\pep_acpi_object_type.htm
old-project: kernel
ms.assetid: 81875C20-8E0E-4BAC-B85F-3D275F8B4708
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE enumeration [Kernel-Mode Driver Architecture], PepAcpiObjectTypeMaximum, PepAcpiObjectTypeMethod, _PEP_ACPI_OBJECT_TYPE, kernel.pep_acpi_object_type, pepfx/PEP_ACPI_OBJECT_TYPE, pepfx/PepAcpiObjectTypeMaximum, pepfx/PepAcpiObjectTypeMethod"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_OBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_TYPE, *PPEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE, *PPEP_ACPI_OBJECT_TYPE
---

# _PEP_ACPI_OBJECT_TYPE Enumeration
The <b>PEP_ACPI_OBJECT_TYPE</b> enumeration indicates the type of ACPI object.

## Syntax
````
typedef enum _PEP_ACPI_OBJECT_TYPE { 
  PepAcpiObjectTypeMethod,
  PepAcpiObjectTypeMaximum
} PEP_ACPI_OBJECT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PepAcpiObjectTypeMethod</td>
                    <td>The object is an ACPI control method.</td>
                </tr>
            
                <tr>
                    <td>PepAcpiObjectTypeDevice</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>PepAcpiObjectTypeMaximum</td>
                    <td>Reserved for use by the operating system.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is an <b>PEP_ACPI_OBJECT_TYPE</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>