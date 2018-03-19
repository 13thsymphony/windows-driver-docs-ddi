---
UID: NS:avc._AVCCONNECTINFO
title: "_AVCCONNECTINFO"
author: windows-driver-content
description: The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avcconnectinfo.htm
old-project: stream
ms.assetid: ed6e01f0-fa30-4a42-8271-70afb2fde8c9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVCCONNECTINFO, AVCCONNECTINFO, AVCCONNECTINFO structure [Streaming Media Devices], PAVCCONNECTINFO, PAVCCONNECTINFO structure pointer [Streaming Media Devices], _AVCCONNECTINFO, avc/AVCCONNECTINFO, avc/PAVCCONNECTINFO, avcref_41c8705a-5735-4ab2-87f0-02b55b128c23.xml, stream.avcconnectinfo"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
-	avc.h
api_name:
-	AVCCONNECTINFO
product: Windows
targetos: Windows
req.typenames: AVCCONNECTINFO, *PAVCCONNECTINFO
---

# _AVCCONNECTINFO structure
The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.

## Syntax
````
typedef struct _AVCCONNECTINFO {
  GUID           DeviceID;
  UCHAR          SubunitAddress[AVCCONNECTINFO_MAX_SUBUNITADDR_LEN];
  ULONG          SubunitPlugNumber;
  KSPIN_DATAFLOW DataFlow;
  HANDLE         hPlug;
  ULONG          UnitPlugNumber;
} AVCCONNECTINFO, *PAVCCONNECTINFO;
````

## Members


`DeviceID`

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.

`SubunitAddress`

The encoded subunit type and subunit ID of the subunit.

`SubunitPlugNumber`

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

`DataFlow`

The direction of data flow on this subunit plug. Destination plugs have KSPIN_DATAFLOW_IN; source plugs have KSPIN_DATAFLOW_OUT.

`hPlug`

A plug handle obtained from <i>61883.sys</i> by the intersect handler according to the bit flags set in the associated AVCPRECONNECTINFO structure for this pin. If the proposed connection is between two subunits within the same unit, this value is <b>NULL</b>.

`UnitPlugNumber`

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

## Remarks
This structure is used only as member inside the <a href="..\avc\ns-avc-_avc_setconnect_info.md">AVC_SETCONNECT_INFO</a> structure. It is not used by itself.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>