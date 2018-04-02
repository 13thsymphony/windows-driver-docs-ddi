---
UID: NE:bthhfpddi._HFP_BYPASS_CODEC_ID_VERSION
title: "_HFP_BYPASS_CODEC_ID_VERSION"
author: windows-driver-content
description: The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.
old-location: audio\hfp_bypass_codec_id_version.htm
old-project: audio
ms.assetid: A16980CD-3F2F-4A67-902A-F3D72AA042D9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PHFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION enumeration [Audio Devices], REQ_HFP_BYPASS_CODEC_ID_V1, _HFP_BYPASS_CODEC_ID_VERSION, audio.hfp_bypass_codec_id_version, bthhfpddi/HFP_BYPASS_CODEC_ID_VERSION, bthhfpddi/REQ_HFP_BYPASS_CODEC_ID_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	HFP_BYPASS_CODEC_ID_VERSION
product:
- Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# _HFP_BYPASS_CODEC_ID_VERSION Enumeration
The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.

## Syntax
```
typedef enum _HFP_BYPASS_CODEC_ID_VERSION {
  REQ_HFP_BYPASS_CODEC_ID_V1
} HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION;
```

## Constants

<table>
            
                <tr>
                    <td>REQ_HFP_BYPASS_CODEC_ID_V1</td>
                    <td>Codec ID structure version 1.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | bthhfpddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn913703">HFP_BYPASS_CODEC_ID_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn798965">IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</a>