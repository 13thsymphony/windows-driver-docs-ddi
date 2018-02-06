---
UID: NS:bdatypes._BDA_CAS_CHECK_ENTITLEMENTTOKEN
title: "_BDA_CAS_CHECK_ENTITLEMENTTOKEN"
author: windows-driver-content
description: "."
old-location: stream\bda_cas_check_entitlementtoken.htm
old-project: stream
ms.assetid: B6B645DF-AB4C-42FE-A664-AF9C9DD4F9E6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BDA_CAS_CHECK_ENTITLEMENTTOKEN, *PBDA_CAS_CHECK_ENTITLEMENTTOKEN, BDA_CAS_CHECK_ENTITLEMENTTOKEN structure [Streaming Media Devices], PBDA_CAS_CHECK_ENTITLEMENTTOKEN, bdatypes/PBDA_CAS_CHECK_ENTITLEMENTTOKEN, PBDA_CAS_CHECK_ENTITLEMENTTOKEN structure pointer [Streaming Media Devices], stream.bda_cas_check_entitlementtoken, bdatypes/BDA_CAS_CHECK_ENTITLEMENTTOKEN, _BDA_CAS_CHECK_ENTITLEMENTTOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_CAS_CHECK_ENTITLEMENTTOKEN
product: Windows
targetos: Windows
req.typenames: "*PBDA_CAS_CHECK_ENTITLEMENTTOKEN, BDA_CAS_CHECK_ENTITLEMENTTOKEN"
---

# _BDA_CAS_CHECK_ENTITLEMENTTOKEN structure


## Syntax
````
typedef struct _BDA_CAS_CHECK_ENTITLEMENTTOKEN {
  PBDARESULT lResult;
  ULONG      ulDescrambleStatus;
} BDA_CAS_CHECK_ENTITLEMENTTOKEN, *PBDA_CAS_CHECK_ENTITLEMENTTOKEN;
````

## Members


`lResult`



`ulDescrambleStatus`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |