---
UID : NS:hbapiwmi._SM_RemovePersistentBinding_IN
title : "_SM_RemovePersistentBinding_IN"
author : windows-driver-content
description : The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.
old-location : storage\sm_removepersistentbinding_in.htm
old-project : storage
ms.assetid : 47e6a189-4b16-411a-8552-3e6f998516ba
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : SM_RemovePersistentBinding_IN, hbapiwmi/PSM_RemovePersistentBinding_IN, storage.sm_removepersistentbinding_in, structs-Fibre_d27cd5dc-07ee-470c-ad0d-239f1d378841.xml, PSM_RemovePersistentBinding_IN structure pointer [Storage Devices], PSM_RemovePersistentBinding_IN, _SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN, SM_RemovePersistentBinding_IN structure [Storage Devices], hbapiwmi/SM_RemovePersistentBinding_IN
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
req.typenames : SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN
---

# _SM_RemovePersistentBinding_IN structure
The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.

## Syntax
````
typedef struct _SM_RemovePersistentBinding_IN {
  UCHAR                 HbaPortWWN[8];
  UCHAR                 DomainPortWWN[8];
  ULONG                 EntryCount;
  MS_SMHBA_BINDINGENTRY Entry[1];
} SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN;
````

## Members


`DomainPortWWN`

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

`Entry`

An array of structures of type SMHBA_SCSIENTRY that describes an HBA's bindings between the operating system and the SAS identifiers.

`EntryCount`

The total number of persistent bindings that are associated with the HBA.

`HbaPortWWN`

The worldwide name (WWN) of the local port whose events the WMI client will receive.

## Remarks
The WMI tool suite generates a declaration of the SM_RemovePersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |