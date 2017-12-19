---
UID: NS.HBAPIWMI._SM_GETPERSISTENTBINDING_IN
title: _SM_GetPersistentBinding_IN
author: windows-driver-content
description: The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.
old-location: storage\sm_getpersistentbinding_in.htm
old-project: storage
ms.assetid: 6c716394-1e82-40d2-befc-50a0ea88f750
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SM_GetPersistentBinding_IN, PSM_GetPersistentBinding_IN, *PSM_GetPersistentBinding_IN, SM_GetPersistentBinding_IN
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
req.alt-api: SM_GetPersistentBinding_IN
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

# _SM_GetPersistentBinding_IN structure



## -description
The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.



## -syntax

````
typedef struct _SM_GetPersistentBinding_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG InEntryCount;
} SM_GetPersistentBinding_IN, *PSM_GetPersistentBinding_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


## -remarks
The WMI tool suite generates a declaration of the SM_GetPersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.


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