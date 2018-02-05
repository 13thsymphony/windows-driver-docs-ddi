---
UID : NS:hbapiwmi._SM_GetTargetMapping_IN
title : "_SM_GetTargetMapping_IN"
author : windows-driver-content
description : The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.
old-location : storage\sm_gettargetmapping_in.htm
old-project : storage
ms.assetid : d6f73582-5eaf-452f-ad5a-cdf5ab99d809
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PSM_GetTargetMapping_IN structure pointer [Storage Devices], hbapiwmi/PSM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN, PSM_GetTargetMapping_IN, structs-Fibre_0109f5f0-dd0c-4a30-8b0a-aa33a54b5a61.xml, SM_GetTargetMapping_IN structure [Storage Devices], _SM_GetTargetMapping_IN, storage.sm_gettargetmapping_in, SM_GetTargetMapping_IN, hbapiwmi/SM_GetTargetMapping_IN
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
req.typenames : SM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN
---

# _SM_GetTargetMapping_IN structure
The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.

## Syntax
````
typedef struct _SM_GetTargetMapping_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG InEntryCount;
} SM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN;
````

## Members


`DomainPortWWN`

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

`HbaPortWWN`

The worldwide name (WWN) of the local port whose events the WMI client will receive.

`InEntryCount`

The number of persistent bindings that are associated with the HBA.

## Remarks
The WMI tool suite generates a declaration of the SM_GetTargetMapping_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |