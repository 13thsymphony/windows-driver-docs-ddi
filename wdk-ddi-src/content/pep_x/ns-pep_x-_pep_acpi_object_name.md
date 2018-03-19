---
UID: NS:pep_x._PEP_ACPI_OBJECT_NAME
title: "_PEP_ACPI_OBJECT_NAME"
author: windows-driver-content
description: The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object.
old-location: kernel\pep_acpi_object_name.htm
old-project: kernel
ms.assetid: 55D8A977-DA91-4CB5-8549-E1CB1731256C
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME union [Kernel-Mode Driver Architecture], _PEP_ACPI_OBJECT_NAME, kernel.pep_acpi_object_name, pepfx/PEP_ACPI_OBJECT_NAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_OBJECT_NAME
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME
---

# _PEP_ACPI_OBJECT_NAME structure
The <b>PEP_ACPI_OBJECT_NAME</b> union contains the four-character name of an ACPI object.

## Syntax
````
typedef union _PEP_ACPI_OBJECT_NAME {
  UCHAR ObjectName[4];
  ULONG ObjectNameAsUlong;
} PEP_ACPI_OBJECT_NAME;
````

## Members


`Name`



`NameAsUlong`



## Remarks
The <i>Name</i> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union. Also, the <i>Name</i> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>