---
UID: NS:61883._CMP_CONNECT_VER2
title: "_CMP_CONNECT_VER2"
author: windows-driver-content
description: This structure contains information for a connection request. The request attempts to make a connection to a plug control register on the local host.
old-location: ieee\cmp_connect_ver2.htm
old-project: IEEE
ms.assetid: 2A2C1478-0512-4F84-90B9-B9C62B5D44DA
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_CONNECT, *PCMP_CONNECT_VER2, 61883/CMP_CONNECT_VER2, 61883/PCMP_CONNECT_VER2, CMP_CONNECT, CMP_CONNECT_VER2, CMP_CONNECT_VER2 structure, IEEE.cmp_connect_ver2, PCMP_CONNECT_VER2, PCMP_CONNECT_VER2 structure pointer, _CMP_CONNECT_VER2"
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
-	CMP_CONNECT_VER2
product:
- Windows
targetos: Windows
req.typenames: CMP_CONNECT_VER2, *PCMP_CONNECT_VER2
---

# _CMP_CONNECT_VER2 structure
This structure contains information for a connection request. The  request attempts to make a connection to a plug control register on the local host.

## Syntax
```
typedef struct _CMP_CONNECT_VER2 {
  IN HANDLE               hOutputPlug;
  IN HANDLE               hInputPlug;
  IN CMP_CONNECT_TYPE     Type;
  IN CIP_DATA_FORMAT_VER2 Format;
  OUT HANDLE              hConnect;
} *PCMP_CONNECT_VER2, CMP_CONNECT_VER2;
```

## Members


`hOutputPlug`

On input, a handle to the output plug to use for the connection. If <b>hOutputPlug</b> is <b>NULL</b>, the connection is for input only.

`hInputPlug`

On input, handle to the input plug to use for the connection. If <b>hInputPlug</b> is <b>NULL</b>, the connection is for output only.

`Type`

On input, the type of the requested connection.

The type of connection to make. Can be one of the following:





#### CMP_Broadcast

A broadcast connection.  



#### CMP_PointToPoint

A connection between a single output plug and one or more input plugs.

`Format`

The requested data format.

On input, a pointer to a <a href="https://msdn.microsoft.com/C78543F5-82CC-43CF-8769-1E721C17FF9C">CIP_DATA_FORMAT_VER2</a> structure that specifies the format of the connection.

`hConnect`

On output, the handle for the created connection.

## Remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>