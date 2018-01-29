---
UID : NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
title : D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
author : windows-driver-content
description : Specifies information used to retrieve a list of profiles.
old-location : display\d3d12ddi_video_decode_profiles_data.htm
old-project : display
ms.assetid : D6615DE8-5103-470D-A895-6663B2CC9261
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020, D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 structure [Display Devices], display.d3d12ddi_video_decode_profiles_data, d3d12umddi/D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
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
req.typenames : D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 structure
Specifies information used to retrieve a list of profiles.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 {
  UINT NodeIndex;
  UINT ProfileCount;
  GUID *pProfiles;
} D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020;
````

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`pProfiles`

A pointer to the returned supported profiles.  The calling application allocates storage for the profile list.

`ProfileCount`

The number of profiles to retrieve.  The runtime ensures this value matches the value returned from PFND3D12DDI_VIDEO_GETCAPS with D3D12DDI_CAPSTYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_COUNT.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |