---
UID: NS.HBAPIWMI._SM_ADDLINK_OUT
title: _SM_AddLink_OUT
author: windows-driver-content
description: The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.
old-location: storage\sm_addlink_out.htm
old-project: storage
ms.assetid: 1c69b8b0-fe73-4e13-be09-70b99e0e3f32
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SM_AddLink_OUT, *PSM_AddLink_OUT, SM_AddLink_OUT
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
req.alt-api: SM_AddLink_OUT
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

# _SM_AddLink_OUT structure



## -description
The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.



## -syntax

````
typedef struct _SM_AddLink_OUT {
  ULONG HBAStatus;
} SM_AddLink_OUT, *PSM_AddLink_OUT;
````


## -struct-fields

### -field HBAStatus

A value associated with the WMI class qualifier <a href="storage.hba_status">HBA_STATUS</a> that indicates the result of an HBA query operation.


## -remarks
The WMI tool suite generates a declaration of the SM_AddLink_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.


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