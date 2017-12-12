---
UID: NS.HBAPIWMI._SM_REMOVELINK_OUT
title: _SM_RemoveLink_OUT
author: windows-driver-content
description: The SM_RemoveLink_OUT structure is used to receive output parameters from the SM_RemoveLink WMI method.
old-location: storage\sm_removelink_out.htm
old-project: storage
ms.assetid: f3b82d62-8596-4bb9-b20b-39f232527d7a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SM_RemoveLink_OUT, SM_RemoveLink_OUT, *PSM_RemoveLink_OUT
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
req.alt-api: SM_RemoveLink_OUT
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

# _SM_RemoveLink_OUT structure



## -description
The SM_RemoveLink_OUT structure is used to receive output parameters from the SM_RemoveLink WMI method.



## -syntax

````
typedef struct _SM_RemoveLink_OUT {
  ULONG HBAStatus;
} SM_RemoveLink_OUT, *PSM_RemoveLink_OUT;
````


## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.


## -remarks
The WMI tool suite generates a declaration of the SM_RemoveLink_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.


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