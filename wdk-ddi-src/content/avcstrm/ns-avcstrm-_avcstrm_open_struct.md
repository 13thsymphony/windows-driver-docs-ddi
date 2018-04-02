---
UID: NS:avcstrm._AVCSTRM_OPEN_STRUCT
title: "_AVCSTRM_OPEN_STRUCT"
author: windows-driver-content
description: The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.
old-location: stream\avcstrm_open_struct.htm
old-project: stream
ms.assetid: c16a2f3c-a5be-4132-920a-b81f67c5ea02
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT structure [Streaming Media Devices], PAVCSTRM_OPEN_STRUCT, PAVCSTRM_OPEN_STRUCT structure pointer [Streaming Media Devices], _AVCSTRM_OPEN_STRUCT, avcsref_6ed25af3-808f-4b20-88c8-e7d2cca25494.xml, avcstrm/AVCSTRM_OPEN_STRUCT, avcstrm/PAVCSTRM_OPEN_STRUCT, stream.avcstrm_open_struct"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	AVCSTRM_OPEN_STRUCT
product:
- Windows
targetos: Windows
req.typenames: AVCSTRM_OPEN_STRUCT, *PAVCSTRM_OPEN_STRUCT
---

# _AVCSTRM_OPEN_STRUCT structure
The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.

## Syntax
```
typedef struct _AVCSTRM_OPEN_STRUCT {
  KSPIN_DATAFLOW       DataFlow;
  PAVCSTRM_FORMAT_INFO AVCFormatInfo;
  PVOID                AVCStreamContext;
  HANDLE               hPlugLocal;
} AVCSTRM_OPEN_STRUCT, *PAVCSTRM_OPEN_STRUCT;
```

## Members


`DataFlow`

Specifies the direction of the data-flow.

`AVCFormatInfo`

Pointer to a description of the subunit stream format.

`AVCStreamContext`

Pointer to a stream context (handle) that is passed to subsequent <i>avcstrm.sys</i> operations. Its content should not be used or altered.

`hPlugLocal`

Specifies a local plug created by an AV/C subunit, which is used to connect to the target device.

## Remarks
The <b>AVCSTRM_OPEN</b> function code uses this structure to describe the open operation. If the operation is successful, a stream context (handle) is returned to the caller in the <b>AVCStrmContext </b>member of this structure, <i>not</i> the <b>AVCStrmContext</b> member in the AVC_STREAM_REQUEST_BLOCK structure.

This value can then be used in subsequent <i>avcstrm.sys</i> operations by placing it in the <b>AVCStrmContext</b> member of the AVC_STREAM_REQUEST_BLOCK structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avcstrm.h (include Avcstrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554117">AVCSTRM_FORMAT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>