---
UID: NF:drmk.DrmGetContentRights
title: DrmGetContentRights function
author: windows-driver-content
description: The DrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID.
old-location: audio\drmgetcontentrights.htm
old-project: audio
ms.assetid: 706a5749-e288-4275-84fc-e500a848d541
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: DrmGetContentRights, DrmGetContentRights function [Audio Devices], aud-prop2_9f836831-bb65-45d1-8701-4aaa77999b81.xml, audio.drmgetcontentrights, drmk/DrmGetContentRights
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
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
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Drmk.lib
-	Drmk.dll
api_name:
-	DrmGetContentRights
product:
- Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---


# DrmGetContentRights function
The <code>DrmGetContentRights</code> function retrieves the DRM content rights assigned to a DRM content ID.

## Syntax

```
NTSTATUS DrmGetContentRights(
  ULONG      ContentId,
  PDRMRIGHTS DrmRights
);
```

## Parameters

`ContentId`

Specifies the DRM content ID. This parameter identifies a KS audio stream.

`DrmRights`

Specifies the DRM content rights that are assigned to the stream that is identified by <i>ContentId</i>. This parameter is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a> structure.


## Return Value

<code>DrmGetContentRights</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

Before a KS audio filter begins mixing together several KS audio streams, it first calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a> to create a content ID for the composite stream. Next, it calls <code>DrmGetContentRights</code> to get the content rights that the system has assigned to the stream.

A module that lies downstream from the KS filter that creates the content ID typically does not need to call <code>DrmGetContentRights</code>. Instead, the module receives both the content ID and content rights either from the system (through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a> call or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request) or directly from the preceding module in the data path (through a call to a content handler). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>.

<code>DrmGetContentRights</code> performs the same function as <a href="https://msdn.microsoft.com/library/windows/hardware/ff537700">PcGetContentRights</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536588">IDrmPort::GetContentRights</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | drmk.h (include Drmk.h) |
| **Library** | Drmk.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536588">IDrmPort::GetContentRights</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537700">PcGetContentRights</a>