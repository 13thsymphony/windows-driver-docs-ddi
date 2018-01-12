---
UID: NS:hbapiwmi._SM_SendSMPPassThru_OUT
title: _SM_SendSMPPassThru_OUT
author: windows-driver-content
description: The SM_SendSMPPassThru_OUT structure is used to receive output parameters from the SM_SendSMPPassThru method.
old-location: storage\sm_sendsmppassthru_out.htm
old-project: storage
ms.assetid: eb173171-3990-405e-b740-8c1a0c915165
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_SendSMPPassThru_OUT, SM_SendSMPPassThru_OUT, *PSM_SendSMPPassThru_OUT
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
req.alt-api: SM_SendSMPPassThru_OUT
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
req.typenames: SM_SendSMPPassThru_OUT, *PSM_SendSMPPassThru_OUT
---

# _SM_SendSMPPassThru_OUT structure



## -description
The SM_SendSMPPassThru_OUT structure is used to receive output parameters from the SM_SendSMPPassThru method.



## -syntax

````
typedef struct _SM_SendSMPPassThru_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendSMPPassThru_OUT, *PSM_SendSMPPassThru_OUT;
````


## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.


### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.


### -field RespBuffer

The results of the common transport command.


## -remarks
The WMI tool suite generates a declaration of the SM_SendSMPPassThru_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.


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