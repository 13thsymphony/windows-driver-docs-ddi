---
UID: NS.HBAPIWMI._SM_SENDSRL_OUT
title: _SM_SendSRL_OUT
author: windows-driver-content
description: The SM_SendSRL_OUT structure is used to receive output parameters from the SM_SendSRL method.
old-location: storage\sm_sendsrl_out.htm
old-project: storage
ms.assetid: 1e6d1a97-b175-4f76-8f4d-15ec089538e8
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SM_SendSRL_OUT, SM_SendSRL_OUT, *PSM_SendSRL_OUT
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
req.alt-api: SM_SendSRL_OUT
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

# _SM_SendSRL_OUT structure



## -description
The SM_SendSRL_OUT structure is used to receive output parameters from the SM_SendSRL method.


## -syntax

````
typedef struct _SM_SendSRL_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendSRL_OUT, *PSM_SendSRL_OUT;
````


## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.

### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.

### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.

### -field RespBuffer

The results of the common transport command.

## -remarks
The WMI tool suite generates a declaration of the SM_SendSRL_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

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