---
UID : NS:bdatypes._BDA_WMDRM_STATUS
title : "_BDA_WMDRM_STATUS"
author : windows-driver-content
description : "."
old-location : stream\bda_wmdrm_status.htm
old-project : stream
ms.assetid : FEE7B3B2-2433-4772-8E79-C325ECC343FF
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.bda_wmdrm_status, bdatypes/PBDA_WMDRM_STATUS, PBDA_WMDRM_STATUS, BDA_WMDRM_STATUS structure [Streaming Media Devices], bdatypes/BDA_WMDRM_STATUS, _BDA_WMDRM_STATUS, BDA_WMDRM_STATUS, PBDA_WMDRM_STATUS structure pointer [Streaming Media Devices], *PBDA_WMDRM_STATUS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : 
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PBDA_WMDRM_STATUS, BDA_WMDRM_STATUS"
---

# _BDA_WMDRM_STATUS structure


## Syntax
````
typedef struct _BDA_WMDRM_STATUS {
  PBDARESULT lResult;
  ULONG      ulMaxCaptureTokenSize;
  ULONG      uMaxStreamingPid;
  ULONG      ulMaxLicense;
  ULONG      ulMinSecurityLevel;
  ULONG      ulRevInfoSequenceNumber;
  ULONGLONG  ulRevInfoIssuedTime;
  ULONG      ulRevListVersion;
  ULONG      ulRevInfoTTL;
  ULONG      ulState;
} BDA_WMDRM_STATUS, *PBDA_WMDRM_STATUS;
````

## Members


`lResult`



`ulMaxCaptureTokenSize`



`ulMaxLicense`



`ulMinSecurityLevel`



`ulRevInfoIssuedTime`



`ulRevInfoSequenceNumber`



`ulRevInfoTTL`



`ulRevListVersion`



`ulState`



`uMaxStreamingPid`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |