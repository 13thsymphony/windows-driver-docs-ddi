---
UID : NS:hbapiwmi._SM_SendRNID_IN
title : _SM_SendRNID_IN
author : windows-driver-content
description : The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.
old-location : storage\sm_sendrnid_in.htm
old-project : storage
ms.assetid : 7d94fc94-bfc6-4666-a321-71a0643f3140
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : hbapiwmi/PSM_SendRNID_IN, SM_SendRNID_IN, PSM_SendRNID_IN structure pointer [Storage Devices], PSM_SendRNID_IN, *PSM_SendRNID_IN, SM_SendRNID_IN structure [Storage Devices], storage.sm_sendrnid_in, _SM_SendRNID_IN, structs-Fibre_61452dff-7706-4a0a-838a-5220f7117668.xml, hbapiwmi/SM_SendRNID_IN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSM_SendRNID_IN, SM_SendRNID_IN"
---

# _SM_SendRNID_IN structure
The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.

## Syntax
````
typedef struct _SM_SendRNID_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG NodeIdDataFormat;
  ULONG InRespBufferMaxSize;
} SM_SendRNID_IN, *PSM_SendRNID_IN;
````

## Members


`DestFCID`

The address identifier of the destination port.

`DestWWN`

The worldwide name (WWN) of the destination port.

`HbaPortWWN`

The worldwide name (WWN) of the local port.

`InRespBufferMaxSize`

The maximum response buffer size.

`NodeIdDataFormat`

The node identification data format.

## Remarks
The WMI tool suite generates a declaration of the SM_SendRNID_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |