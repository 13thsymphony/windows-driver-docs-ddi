---
UID: NS:hbapiwmi._SM_SendRNID_IN
title: "_SM_SendRNID_IN"
author: windows-driver-content
description: The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.
old-location: storage\sm_sendrnid_in.htm
old-project: storage
ms.assetid: 7d94fc94-bfc6-4666-a321-71a0643f3140
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSM_SendRNID_IN, PSM_SendRNID_IN, PSM_SendRNID_IN structure pointer [Storage Devices], SM_SendRNID_IN, SM_SendRNID_IN structure [Storage Devices], _SM_SendRNID_IN, hbapiwmi/PSM_SendRNID_IN, hbapiwmi/SM_SendRNID_IN, storage.sm_sendrnid_in, structs-Fibre_61452dff-7706-4a0a-838a-5220f7117668.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	SM_SendRNID_IN
product:
- Windows
targetos: Windows
req.typenames: SM_SendRNID_IN, *PSM_SendRNID_IN
---

# _SM_SendRNID_IN structure
The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.

## Syntax
```
typedef struct _SM_SendRNID_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG NodeIdDataFormat;
  ULONG InRespBufferMaxSize;
} *PSM_SendRNID_IN, SM_SendRNID_IN;
```

## Members


`HbaPortWWN`

The worldwide name (WWN) of the local port.

`DestWWN`

The worldwide name (WWN) of the destination port.

`DestFCID`

The address identifier of the destination port.

`NodeIdDataFormat`

The node identification data format.

`InRespBufferMaxSize`

The maximum response buffer size.

## Remarks
The WMI tool suite generates a declaration of the SM_SendRNID_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |