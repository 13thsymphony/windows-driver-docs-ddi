---
UID : NS:acpitabl._GIC_ITS
title : _GIC_ITS
author : windows-driver-content
description : This topic describes the GIC_ITS structure.
old-location : acpi\gic_its.htm
old-project : acpi
ms.assetid : C0DA1B09-230E-4DE6-98CD-F80243D63B95
ms.author : windowsdriverdev
ms.date : 12/31/2017
ms.keywords : _GIC_ITS, GIC_ITS, *PGIC_ITS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : acpitabl.h
req.include-header : Acpitabl.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709 and later versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GIC_ITS
req.alt-loc : Acpitabl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : GIC_ITS
---

# _GIC_ITS structure
This topic describes the <b>GIC_ITS</b> structure.

## Syntax
````
typedef struct _GIC_ITS {
  UCHAR     Type;
  UCHAR     Length;
  USHORT    Reserved1;
  ULONG     Identifier;
  ULONGLONG PhysicalAddress;
  ULONG     Reserved2;
} GIC_ITS;
````

## Members

        
            `Identifier`

            Defines the <b>ULONG</b> member <b>Identifier</b>.
        
            `Length`

            Defines the <b>UCHAR</b> member <b>Length</b>.
        
            `PhysicalAddress`

            Defines the <b>ULONGLONG</b> member <b>PhysicalAddress</b>.
        
            `Reserved1`

            Reserved for future use.
        
            `Reserved2`

            Reserved for future use.
        
            `Type`

            Defines the <b>UCHAR</b> member <b>Type</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | acpitabl.h (include Acpitabl.h) |