---
UID: NS.HBAPIWMI._SM_REMOVEPERSISTENTBINDING_IN
title: _SM_RemovePersistentBinding_IN
author: windows-driver-content
description: The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.
old-location: storage\sm_removepersistentbinding_in.htm
old-project: storage
ms.assetid: 47e6a189-4b16-411a-8552-3e6f998516ba
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN, SM_RemovePersistentBinding_IN, PSM_RemovePersistentBinding_IN
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
req.alt-api: SM_RemovePersistentBinding_IN
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
---

# _SM_RemovePersistentBinding_IN structure



## -description
The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.



## -syntax

````
typedef struct _SM_RemovePersistentBinding_IN {
  UCHAR                 HbaPortWWN[8];
  UCHAR                 DomainPortWWN[8];
  ULONG                 EntryCount;
  MS_SMHBA_BINDINGENTRY Entry[1];
} SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field EntryCount

The total number of persistent bindings that are associated with the HBA.


### -field Entry

An array of structures of type SMHBA_SCSIENTRY that describes an HBA's bindings between the operating system and the SAS identifiers.


## -remarks
The WMI tool suite generates a declaration of the SM_RemovePersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>