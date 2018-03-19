---
UID: NS:61883._CMP_CONNECT_VER3
title: "_CMP_CONNECT_VER3"
author: windows-driver-content
description: This structure contains information for a connection request.
old-location: ieee\cmp_connect_ver3.htm
old-project: IEEE
ms.assetid: 1F2C2B8E-6535-40F1-A5D3-46DAD43E923E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_CONNECT, *PCMP_CONNECT_VER3, 61883/CMP_CONNECT_VER3, 61883/PCMP_CONNECT_VER3, CMP_CONNECT, CMP_CONNECT_VER3, CMP_CONNECT_VER3 structure [Buses], IEEE.cmp_connect_ver3, PCMP_CONNECT_VER3, PCMP_CONNECT_VER3 structure pointer [Buses], _CMP_CONNECT_VER3"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CMP_CONNECT_VER3
product: Windows
targetos: Windows
req.typenames: CMP_CONNECT_VER3, *PCMP_CONNECT_VER3
---

# _CMP_CONNECT_VER3 structure
This structure contains information for a connection request.

## Syntax
````
typedef struct _CMP_CONNECT_VER3 {
  HANDLE               hOutputPlug;
  HANDLE               hInputPlug;
  CMP_CONNECT_TYPE     Type;
  CIP_DATA_FORMAT_VER3 Format;
  HANDLE               hConnect;
} CMP_CONNECT_VER3, *PCMP_CONNECT_VER3;
````

## Members


`hOutputPlug`

The handle of an output plug.

`hInputPlug`

The handle of an input plug.

`Type`

The type of the requested connection.

`Format`

The requested data format.

`hConnect`

The handle for the created connection.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>