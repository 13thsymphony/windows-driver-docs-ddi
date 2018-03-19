---
UID: NS:bthioctl._BTH_SDP_SERVICE_SEARCH_REQUEST
title: "_BTH_SDP_SERVICE_SEARCH_REQUEST"
author: windows-driver-content
description: The BTH_SDP_SERVICE_SEARCH_REQUEST structure contains information pertinent to an SDP service search.
old-location: bltooth\bth_sdp_service_search_request.htm
old-project: bltooth
ms.assetid: d1ef833e-8350-499c-9a3d-408d900c9245
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_SDP_SERVICE_SEARCH_REQUEST, BTH_SDP_SERVICE_SEARCH_REQUEST, BTH_SDP_SERVICE_SEARCH_REQUEST structure [Bluetooth Devices], PBTH_SDP_SERVICE_SEARCH_REQUEST, PBTH_SDP_SERVICE_SEARCH_REQUEST structure pointer [Bluetooth Devices], _BTH_SDP_SERVICE_SEARCH_REQUEST, bltooth.bth_sdp_service_search_request, bth_structs_c625eff6-6ec7-49a4-a141-778ebda2d563.xml, bthioctl/BTH_SDP_SERVICE_SEARCH_REQUEST, bthioctl/PBTH_SDP_SERVICE_SEARCH_REQUEST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthioctl.h
api_name:
-	BTH_SDP_SERVICE_SEARCH_REQUEST
product: Windows
targetos: Windows
req.typenames: BTH_SDP_SERVICE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_SEARCH_REQUEST
---

# _BTH_SDP_SERVICE_SEARCH_REQUEST structure
The BTH_SDP_SERVICE_SEARCH_REQUEST structure contains information pertinent to an SDP service
  search.

## Syntax
````
typedef struct _BTH_SDP_SERVICE_SEARCH_REQUEST {
  HANDLE_SDP   hConnection;
  SdpQueryUuid uuids[MAX_UUIDS_IN_QUERY];
} BTH_SDP_SERVICE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_SEARCH_REQUEST;
````

## Members


`HANDLE_SDP_FIELD_NAME`



`uuids`

An array of UUIDs that represent the services for which to query. Each entry can be a 2-byte,
     4-byte, or 16-byte type, and there can be a maximum of 12 entries. The array can be terminated before
     all 12 entries are used if a UUID entry contains all zeros.

## Remarks
This structure is passed as the input buffer to the 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md">
    IOCTL_BTH_SDP_SERVICE_SEARCH</a> IOCTL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthioctl.h (include Bthioctl.h) |

## See Also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md">IOCTL_BTH_SDP_SERVICE_SEARCH</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>