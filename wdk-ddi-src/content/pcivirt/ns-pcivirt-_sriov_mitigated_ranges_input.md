---
UID : NS:pcivirt._SRIOV_MITIGATED_RANGES_INPUT
title : _SRIOV_MITIGATED_RANGES_INPUT
author : windows-driver-content
description : This structure is the input buffer in the IOCTL_SRIOV_QUERY_MITIGATED_RANGES request to get the specific ranges on which intercepts must be placed.
old-location : pci\sriov_mitigated_ranges_input.htm
old-project : PCI
ms.assetid : 40b81630-997f-4427-8d02-5004de6fc943
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SRIOV_MITIGATED_RANGES_INPUT, *PSRIOV_MITIGATED_RANGES_INPUT, SRIOV_MITIGATED_RANGES_INPUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pcivirt.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SRIOV_MITIGATED_RANGES_INPUT
req.alt-loc : pcivirt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PSRIOV_MITIGATED_RANGES_INPUT, SRIOV_MITIGATED_RANGES_INPUT"
---

# _SRIOV_MITIGATED_RANGES_INPUT structure
This structure is the input buffer in the <a href="https://msdn.microsoft.com/58b6e53d-be7a-4563-a27d-db216a12d60d">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> request to get the specific ranges on which intercepts must be placed.

## Syntax
````
typedef struct _SRIOV_MITIGATED_RANGES_INPUT {
  USHORT  VfIndex;
  UCHAR   BarNumber;
} SRIOV_MITIGATED_RANGES_INPUT, SRIOV_MITIGATED_RANGES_INPUT;
````

## Members

        
            `BarNumber`

            The number of BAR of the ranges of memory-mapped I/O space.
        
            `VfIndex`

            Zero-based index of the virtual function from the first virtual function exposed by this physical function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pcivirt.h |