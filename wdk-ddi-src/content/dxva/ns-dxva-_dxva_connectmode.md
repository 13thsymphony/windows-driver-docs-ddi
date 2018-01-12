---
UID: NS:dxva._DXVA_ConnectMode
title: _DXVA_ConnectMode
author: windows-driver-content
description: The DXVA_ConnectMode structure is sent by the host decoder to the accelerator to define the restricted profile used within a DirectX VA connection.
old-location: display\dxva_connectmode.htm
old-project: display
ms.assetid: 84520745-c99d-4495-a7c4-514d5e6cd27e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVA_ConnectMode, *LPDXVA_ConnectMode, DXVA_ConnectMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_ConnectMode
req.alt-loc: dxva.h
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
req.typenames: *LPDXVA_ConnectMode, DXVA_ConnectMode
---

# _DXVA_ConnectMode structure



## -description
The DXVA_ConnectMode structure is sent by the host decoder to the accelerator to define the restricted profile used within a DirectX VA connection.



## -syntax

````
typedef struct _DXVA_ConnectMode {
  GUID guidMode;
  WORD wRestrictedMode;
} DXVA_ConnectMode, *LPDXVA_ConnectMode;
````


## -struct-fields

### -field guidMode

Specifies the GUID associated with the <a href="https://msdn.microsoft.com/043d5867-d761-47eb-99de-5022a9ee6e7f">restricted profile</a> to be used. 


### -field wRestrictedMode

Specifies the numeric identifier of the restricted profile to be used. 


## -remarks
The following GUIDs placed in the <b>guidMode</b> member of this structure set the <a href="https://msdn.microsoft.com/043d5867-d761-47eb-99de-5022a9ee6e7f">restricted profile</a> to be used. The constants that define the GUIDs used are in <i>dxva.h</i>.

DXVA_ModeNone

Nonrestricted

DXVA_ModeH261_A


<a href="https://msdn.microsoft.com/3212a331-06f8-437e-9f04-e8397d16b7b4">H261_A</a>


DXVA_ModeH261_B


<a href="https://msdn.microsoft.com/9a2ccb4b-4bdf-4fb4-ba11-7f43f8423756">H261_B</a>


DXVA_ModeH263_A


<a href="https://msdn.microsoft.com/55ebafec-5924-44e3-96cc-c2b0c6e912c8">H263_A</a>


DXVA_ModeH263_B


<a href="https://msdn.microsoft.com/3a4b8911-caa1-41f3-803a-26a831aa91f0">H263_B</a>


DXVA_ModeH263_C


<a href="https://msdn.microsoft.com/30ddb90d-3947-426c-b780-7214c9cb3b49">H263_C</a>


DXVA_ModeH263_D


<a href="https://msdn.microsoft.com/c25cded7-ea4e-4e82-9200-f90b2bdefc97">H263_D</a>


DXVA_ModeH263_E


<a href="https://msdn.microsoft.com/21022bc6-8102-4727-8f8b-9cec6cce35cb">H263_E</a>


DXVA_ModeH263_F


<a href="https://msdn.microsoft.com/7b7a6b8b-0383-4d2e-84be-d5dd6392c876">H263_F</a>


DXVA_ModeMPEG1_A


<a href="https://msdn.microsoft.com/2c4d79b7-3331-49f9-a561-6e5b609543df">MPEG1_A</a>


DXVA_ModeMPEG2_A


<a href="https://msdn.microsoft.com/4f9e2aad-4072-4a49-87df-dfc6b4bf5f56">MPEG2_A</a>


DXVA_ModeMPEG2_B


<a href="https://msdn.microsoft.com/7d67f0ef-a5eb-40db-9f00-6f652d28e530">MPEG2_B</a>


DXVA_ModeMPEG2_C


<a href="https://msdn.microsoft.com/610ca80d-b29a-4c30-98df-8df8fe825157">MPEG2_C</a>


DXVA_ModeMPEG2_D


<a href="https://msdn.microsoft.com/f5cb5e49-c64c-46d2-92bb-68db1d9c5d18">MPEG2_D</a>


DXVA_ModeH264_A

H264_A

DXVA_ModeH264_B

H264_B

DXVA_ModeH264_C

H264_C

DXVA_ModeH264_D

H264_D

DXVA_ModeH264_E

H264_E

DXVA_ModeH264_F

H264_F

DXVA_ModeWMV8_A


<a href="https://msdn.microsoft.com/ffc203e9-fca4-48d3-842b-d9f75ad7caa0">WMV8_A</a>


DXVA_ModeWMV8_B


<a href="https://msdn.microsoft.com/ffc203e9-fca4-48d3-842b-d9f75ad7caa0">WMV8_B</a>


DXVA_ModeWMV9_A


<a href="https://msdn.microsoft.com/ffc203e9-fca4-48d3-842b-d9f75ad7caa0">WMV9_A</a>


DXVA_ModeWMV9_B


<a href="https://msdn.microsoft.com/ffc203e9-fca4-48d3-842b-d9f75ad7caa0">WMV9_B</a>


DXVA_ModeWMV9_C


<a href="https://msdn.microsoft.com/ffc203e9-fca4-48d3-842b-d9f75ad7caa0">WMV9_C</a>


DXVA_ModeVC1_A

VC1_A

DXVA_ModeVC1_B

VC1_B

DXVA_ModeVC1_C

VC1_C

DXVA_ModeVC1_D

VC1_D

The following restricted mode identifiers placed in the <b>wRestrictedMode</b> member of this structure indicate which restricted profile is used. These identifiers are defined in <i>dxva.h</i>.

DXVA_RESTRICTED_MODE_UNRESTRICTED

DXVA_RESTRICTED_MODE_H261_A

DXVA_RESTRICTED_MODE_H261_B

DXVA_RESTRICTED_MODE_H263_A

DXVA_RESTRICTED_MODE_H263_B

DXVA_RESTRICTED_MODE_H263_C

DXVA_RESTRICTED_MODE_H263_D

DXVA_RESTRICTED_MODE_H263_E

DXVA_RESTRICTED_MODE_H263_F

DXVA_RESTRICTED_MODE_MPEG1_A

DXVA_RESTRICTED_MODE_MPEG2_A

DXVA_RESTRICTED_MODE_MPEG2_B

DXVA_RESTRICTED_MODE_MPEG2_C

DXVA_RESTRICTED_MODE_MPEG2_D

DXVA_RESTRICTED_MODE_H264_A

DXVA_RESTRICTED_MODE_H264_B

DXVA_RESTRICTED_MODE_H264_C

DXVA_RESTRICTED_MODE_H264_D

DXVA_RESTRICTED_MODE_H264_E

DXVA_RESTRICTED_MODE_H264_F

DXVA_RESTRICTED_MODE_WMV8_A

DXVA_RESTRICTED_MODE_WMV8_B

DXVA_RESTRICTED_MODE_WMV9_A

DXVA_RESTRICTED_MODE_WMV9_B

DXVA_RESTRICTED_MODE_WMV9_C

DXVA_RESTRICTED_MODE_VC1_A

DXVA_RESTRICTED_MODE_VC1_B

DXVA_RESTRICTED_MODE_VC1_C

DXVA_RESTRICTED_MODE_VC1_D

For information about the restricted profiles of the MPEG-4 AVC (H.264) and VC-1 video codec standards, download <a href="http://go.microsoft.com/fwlink/p/?linkid=141799">DirectX Video Acceleration Specification for H.264/AVC Decoding</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=141800">DirectX Video Acceleration Specification for Windows Media Video v8, v9 and vA Decoding (Including SMPTE 421M "VC-1")</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>