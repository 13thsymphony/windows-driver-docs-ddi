---
UID : NS:hbapiwmi._SM_GetTargetMapping_OUT
title : _SM_GetTargetMapping_OUT
author : windows-driver-content
description : The SM_GetTargetMapping structure_OUT structure is used to receive output parameters from the SM_GetTargetMapping method.
old-location : storage\sm_gettargetmapping_out.htm
old-project : storage
ms.assetid : 164379fa-15fb-4ab7-9cf8-8403f92d7a42
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : "*PSM_GetTargetMapping_OUT, PSM_GetTargetMapping_OUT structure pointer [Storage Devices], SM_GetTargetMapping_OUT, _SM_GetTargetMapping_OUT, hbapiwmi/PSM_GetTargetMapping_OUT, SM_GetTargetMapping_OUT structure [Storage Devices], structs-Fibre_fd5726b9-b4fe-470a-9e43-65148a60808b.xml, storage.sm_gettargetmapping_out, PSM_GetTargetMapping_OUT, hbapiwmi/SM_GetTargetMapping_OUT"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSM_GetTargetMapping_OUT, SM_GetTargetMapping_OUT"
---

# _SM_GetTargetMapping_OUT structure
The SM_GetTargetMapping structure_OUT structure is used to receive output parameters from the SM_GetTargetMapping method.

## Syntax
````
typedef struct _SM_GetTargetMapping_OUT {
  ULONG              HBAStatus;
  ULONG              TotalEntryCount;
  ULONG              OutEntryCount;
  MS_SMHBA_SCSIENTRY Entry[1];
} SM_GetTargetMapping_OUT, *PSM_GetTargetMapping_OUT;
````

## Members


`Entry`

An array of structures of type SMHBA_SCSIENTRY that describes an HBA's bindings between the operating system and the SAS identifiers.

`HBAStatus`

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`OutEntryCount`

The total number of mappings that are retrieved. This value will be less than or equal to TotalEntryCount.

`TotalEntryCount`

The total number of persistent bindings that are associated with the HBA.

## Remarks
The WMI tool suite generates a declaration of the SM_GetTargetMapping_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |