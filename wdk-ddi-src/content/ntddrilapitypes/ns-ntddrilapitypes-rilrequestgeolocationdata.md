---
UID: NS:ntddrilapitypes.RILREQUESTGEOLOCATIONDATA
title: RILREQUESTGEOLOCATIONDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrequestgeolocationdata.htm
old-project: netvista
ms.assetid: 814e00c5-7248-4853-a61b-e70be86bca0e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilrequestgeolocationdata, RILREQUESTGEOLOCATIONDATA structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILREQUESTGEOLOCATIONDATA, *LPRILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILREQUESTGEOLOCATIONDATA
product: Windows
targetos: Windows
req.typenames: RILREQUESTGEOLOCATIONDATA, *LPRILREQUESTGEOLOCATIONDATA
---

# RILREQUESTGEOLOCATIONDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILREQUESTGEOLOCATIONDATA {
  DWORD                          cbSize;
  DWORD                          dwParams;
  DWORD                          dwExecutor;
  RILGEOLOCATIONTYPEMASK         dwLocationInformationMask;
  RILGEOLOCATIONREQUESTACCURACY  dwLocationRequestAccuracy;
  RILGEOLOCATIONREQUESTINFO      rrRequestInformation;
} RILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA;
````

## Members


`cbSize`



`dwExecutor`



`dwLocationInformationMask`



`dwLocationRequestAccuracy`



`dwParams`



`rrRequestInformation`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |