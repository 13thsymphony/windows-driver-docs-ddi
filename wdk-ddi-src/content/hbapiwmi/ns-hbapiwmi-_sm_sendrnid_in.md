---
UID: NS.HBAPIWMI._SM_SENDRNID_IN
title: _SM_SendRNID_IN
author: windows-driver-content
description: The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.
old-location: storage\sm_sendrnid_in.htm
old-project: storage
ms.assetid: 7d94fc94-bfc6-4666-a321-71a0643f3140
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SM_SendRNID_IN, *PSM_SendRNID_IN, SM_SendRNID_IN, PSM_SendRNID_IN
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
req.alt-api: SM_SendRNID_IN
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

# _SM_SendRNID_IN structure



## -description
The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.



## -syntax

````
typedef struct _SM_SendRNID_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG NodeIdDataFormat;
  ULONG InRespBufferMaxSize;
} SM_SendRNID_IN, *PSM_SendRNID_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port.


### -field DestWWN

The worldwide name (WWN) of the destination port.


### -field DestFCID

The address identifier of the destination port.


### -field NodeIdDataFormat

The node identification data format.


### -field InRespBufferMaxSize

The maximum response buffer size.


## -remarks
The WMI tool suite generates a declaration of the SM_SendRNID_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.


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