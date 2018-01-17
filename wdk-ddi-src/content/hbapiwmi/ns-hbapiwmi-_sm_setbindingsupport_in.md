---
UID: NS:hbapiwmi._SM_SetBindingSupport_IN
title: _SM_SetBindingSupport_IN
author: windows-driver-content
description: The SM_SetBindingSupport_IN structure is used to provide input parameters to the SM_SetBindingSupport method.
old-location: storage\sm_setbindingsupport_in.htm
old-project: storage
ms.assetid: 7bcee845-9b3f-4ad7-843f-1f4cd74ee1be
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_SetBindingSupport_IN, *PSM_SetBindingSupport_IN, SM_SetBindingSupport_IN
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
req.alt-api: SM_SetBindingSupport_IN
req.alt-loc: hbapiwmi.h
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
req.typenames: *PSM_SetBindingSupport_IN, SM_SetBindingSupport_IN
---

# _SM_SetBindingSupport_IN structure



## -description
The SM_SetBindingSupport_IN structure is used to provide input parameters to the SM_SetBindingSupport method.



## -syntax

````
typedef struct _SM_SetBindingSupport_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG Flags;
} SM_SetBindingSupport_IN, *PSM_SetBindingSupport_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field Flags

The HBA_BIND_CAPABILITY binding capabilities.


## -remarks
The WMI tool suite generates a declaration of the SM_SetBindingSupport_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SMHBA_BindingEntry WMI class.</p>