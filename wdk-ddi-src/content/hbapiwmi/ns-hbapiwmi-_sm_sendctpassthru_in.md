---
UID: NS.HBAPIWMI._SM_SENDCTPASSTHRU_IN
title: _SM_SendCTPassThru_IN
author: windows-driver-content
description: The SM_SendCTPassThru_IN structure is used to provide input parameters to the SM_SendCTPassThru method.
old-location: storage\sm_sendctpassthru_in.htm
old-project: storage
ms.assetid: a6dfb1a2-bfc2-4117-8a4e-f52979818289
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SM_SendCTPassThru_IN, SM_SendCTPassThru_IN, *PSM_SendCTPassThru_IN
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
req.alt-api: SM_SendCTPassThru_IN
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

# _SM_SendCTPassThru_IN structure



## -description
The SM_SendCTPassThru_IN structure is used to provide input parameters to the SM_SendCTPassThru method.


## -syntax

````
typedef struct _SM_SendCTPassThru_IN {
  UCHAR HbaPortWWN[8];
  ULONG InRespBufferMaxSize;
  ULONG ReqBufferSize;
  UCHAR ReqBuffer[1];
} SM_SendCTPassThru_IN, *PSM_SendCTPassThru_IN;
````


## -struct-fields

### -field HbaPortWWN

The HBA port worldwide name (WWN) to which pass-through commands will be sent.

### -field InRespBufferMaxSize

The maximum response buffer size.

### -field ReqBufferSize

The size, in bytes, of the buffer that will hold the results of the common transport command.

### -field ReqBuffer


## -remarks
The WMI tool suite generates a declaration of the SM_SendCTPassThru_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

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