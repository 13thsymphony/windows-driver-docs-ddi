---
UID: NS:61883._CMP_GET_PLUG_HANDLE
title: "_CMP_GET_PLUG_HANDLE"
author: windows-driver-content
description: This structure is used in getting the handle of a plug.
old-location: ieee\cmp_get_plug_handle.htm
old-project: IEEE
ms.assetid: 4EDEE2EE-7B42-4CC9-8CFC-4690193C5D4D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_GET_PLUG_HANDLE, 61883/CMP_GET_PLUG_HANDLE, 61883/PCMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE structure [Buses], IEEE.cmp_get_plug_handle, PCMP_GET_PLUG_HANDLE, PCMP_GET_PLUG_HANDLE structure pointer [Buses], _CMP_GET_PLUG_HANDLE"
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
-	CMP_GET_PLUG_HANDLE
product: Windows
targetos: Windows
req.typenames: CMP_GET_PLUG_HANDLE, *PCMP_GET_PLUG_HANDLE
---

# _CMP_GET_PLUG_HANDLE structure
This structure is used in getting the handle of a plug. The  request retrieves a unique handle associated with an input or output plug. The plug handle is required for all operations on the plug. A driver uses a plug handle to get the state of a plug, modify plug settings, or delete a plug. A driver can delete only plugs it has previously created.

## Syntax
````
typedef struct _CMP_GET_PLUG_HANDLE {
  ULONG         PlugNum;
  CMP_PLUG_TYPE Type;
  HANDLE        hPlug;
} CMP_GET_PLUG_HANDLE, *PCMP_GET_PLUG_HANDLE;
````

## Members


`PlugNum`

The number of the plug whose handle was returned by the Av61883_CreatePlug request that created the plug.

`Type`

The type of the plug. This can be CMP_PlugOut for an output plug, or CMP_PlugIn for an input plug.

`hPlug`

On output, a handle to the plug specified with PlugNum and Type.

## Remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>