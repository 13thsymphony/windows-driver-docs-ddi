---
UID: NS.hbapiwmi._SM_SendTEST_OUT
title: SM_SendTEST_OUT
author: windows-driver-content
description: The SM_SendTEST_OUT structure is used to receive output parameters from the SM_SendTEST method.
old-location: storage\sm_sendtest_out.htm
old-project: storage
ms.assetid: e24a2498-7f33-435c-97ad-e4ae283580c2
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SM_SendTEST_OUT, SM_SendTEST_OUT, *PSM_SendTEST_OUT
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
req.alt-api: SM_SendTEST_OUT
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
req.iface: 
---

# SM_SendTEST_OUT structure



## -description
<p>The SM_SendTEST_OUT structure is used to receive output parameters from the SM_SendTEST method.</p>


## -syntax

````
typedef struct _SM_SendTEST_OUT {
  ULONG HBAStatus;
} SM_SendTEST_OUT, *PSM_SendTEST_OUT;
````


## -struct-fields
<dl>

### -field <b>HBAStatus</b>

<dd>
<p>The status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SM_SendTEST_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>