---
UID: NS:hbapiwmi._SM_GetBindingCapability_IN
title: "_SM_GetBindingCapability_IN"
author: windows-driver-content
description: The SM_GetBindingCapability_IN structure is used to provide input parameters to the SM_GetBindingCapability method.
old-location: storage\sm_getbindingcapability_in.htm
old-project: storage
ms.assetid: 9b2d471a-649e-4289-a27a-b78893d8477b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SM_GetBindingCapability_IN structure [Storage Devices], storage.sm_getbindingcapability_in, hbapiwmi/SM_GetBindingCapability_IN, PSM_GetBindingCapability_IN, PSM_GetBindingCapability_IN structure pointer [Storage Devices], _SM_GetBindingCapability_IN, structs-Fibre_0aed53e6-0683-4d6c-94c7-30ee531084ab.xml, hbapiwmi/PSM_GetBindingCapability_IN, *PSM_GetBindingCapability_IN, SM_GetBindingCapability_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_GetBindingCapability_IN
product: Windows
targetos: Windows
req.typenames: "*PSM_GetBindingCapability_IN, SM_GetBindingCapability_IN"
---

# _SM_GetBindingCapability_IN structure
The SM_GetBindingCapability_IN structure is used to provide input parameters to the SM_GetBindingCapability method.

## Syntax
````
typedef struct _SM_GetBindingCapability_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
} SM_GetBindingCapability_IN, *PSM_GetBindingCapability_IN;
````

## Members


`DomainPortWWN`

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

`HbaPortWWN`

The worldwide name (WWN) of the local port whose events the WMI client will receive.

## Remarks
The WMI tool suite generates a declaration of the SM_GetBindingCapability_IN structure in <i>Hbapiwmi.h</i> when it compiles the SM_TargetInformationMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |