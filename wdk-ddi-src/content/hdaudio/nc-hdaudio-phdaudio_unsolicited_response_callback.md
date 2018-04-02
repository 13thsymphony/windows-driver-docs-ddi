---
UID: NC:hdaudio.PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
title: PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
author: windows-driver-content
description: HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function.
old-location: audio\phdaudio_unsolicited_response_callback.htm
old-project: audio
ms.assetid: B98F669D-D0DE-4FF2-903C-D51E0FEEE840
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: HDAudioUnsolicitedResponseCallback, HDAudioUnsolicitedResponseCallback callback function [Audio Devices], PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK, audio.phdaudio_unsolicited_response_callback, hdaudio/HDAudioUnsolicitedResponseCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Hdaudio.h
api_name:
-	HDAudioUnsolicitedResponseCallback
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback function
HDAudio codec unsolicited response callback function. <b>PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK</b> is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537803">PREGISTER_EVENT_CALLBACK</a> callback function.

## Syntax

```
PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK PhdaudioUnsolicitedResponseCallback;

void PhdaudioUnsolicitedResponseCallback(
   HDAUDIO_CODEC_RESPONSE,
   PVOID
)
{...}
```

## Parameters

`HDAUDIO_CODEC_RESPONSE`



`PVOID`




## Return Value

Void

## Remarks

The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | hdaudio.h |
| **IRQL** | PASSIVE_LEVEL |