---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
author: windows-driver-content
description: The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile.
old-location: display\pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count.htm
old-project: display
ms.assetid: BD3DFB48-9470-45CC-93BC-A918FD43DC3F
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count, pfnGetBitstreamEncryptionSchemeCount callback function [Display Devices], pfnGetBitstreamEncryptionSchemeCount, PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, d3d12umddi/pfnGetBitstreamEncryptionSchemeCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
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
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnGetBitstreamEncryptionSchemeCount
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback function
The <i>pfnGetBitstreamEncryptionSchemeCount</i> callback function retrieves the number of encryption schemes supported for a decode profile.

## Syntax

```
PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 Pfnd3d12ddiVideoGetBitstreamEncryptionSchemeCount0020;

UINT Pfnd3d12ddiVideoGetBitstreamEncryptionSchemeCount0020(
   D3D12DDI_HDEVICE,
  UINT NodeIndex,
  REFGUID DecodeProfile
)
{...}
```

## Parameters

`D3D12DDI_HDEVICE`



`NodeIndex`

The physical adapter of the device to which this operation applies.

`DecodeProfile`

The decode profile GUID to retrieve the count of supported encryption GUIDs.


## Return Value

This function retrieves the number of encryption schemes supported for a decode profile.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |