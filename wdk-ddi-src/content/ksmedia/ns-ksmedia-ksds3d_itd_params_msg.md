---
UID: NS:ksmedia.KSDS3D_ITD_PARAMS_MSG
title: KSDS3D_ITD_PARAMS_MSG
author: windows-driver-content
description: The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (KSNODETYPE_3D_EFFECTS).
old-location: audio\ksds3d_itd_params_msg.htm
old-project: audio
ms.assetid: cc580766-54ca-47b2-93dd-2f234afa73ff
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PKSDS3D_ITD_PARAMS_MSG, KSDS3D_ITD_PARAMS_MSG, KSDS3D_ITD_PARAMS_MSG structure [Audio Devices], PKSDS3D_ITD_PARAMS_MSG, PKSDS3D_ITD_PARAMS_MSG structure pointer [Audio Devices], aud-prop_af31be2f-c153-4430-9634-6d29b05208dd.xml, audio.ksds3d_itd_params_msg, ksmedia/KSDS3D_ITD_PARAMS_MSG, ksmedia/PKSDS3D_ITD_PARAMS_MSG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KSDS3D_ITD_PARAMS_MSG
product: Windows
targetos: Windows
req.typenames: KSDS3D_ITD_PARAMS_MSG, *PKSDS3D_ITD_PARAMS_MSG
---

# KSDS3D_ITD_PARAMS_MSG structure
The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>).

## Syntax
````
typedef struct {
  ULONG             Enabled;
  KSDS3D_ITD_PARAMS LeftParams;
  KSDS3D_ITD_PARAMS RightParams;
  ULONG             Reserved;
} KSDS3D_ITD_PARAMS_MSG, *PKSDS3D_ITD_PARAMS_MSG;
````

## Members


`Enabled`

Specifies whether to enable the ITD algorithm. A nonzero value enables the algorithm. Zero disables it. For more information, see the following Remarks section.

`LeftParams`

Specifies the ITD parameters for the left channel (channel 0). This parameter is a structure of type <a href="..\ksmedia\ns-ksmedia-ksds3d_itd_params.md">KSDS3D_ITD_PARAMS</a>.

`Reserved`

Reserved. Set to zero.

`RightParams`

Specifies the ITD parameters for the right channel (channel 1). This parameter is a structure of type KSDS3D_ITD_PARAMS.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537358">KSPROPERTY_ITD3D_PARAMS</a> property request.

The <i>Enabled</i> parameter should track the DirectSound buffer's 3D mode: Disable ITD processing when the 3D mode is disabled, and enable it when the 3D mode is enabled. For more information, see the description of the <b>DirectSound3DBuffer::SetMode</b> method in the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537358">KSPROPERTY_ITD3D_PARAMS</a>



<a href="..\ksmedia\ns-ksmedia-ksds3d_itd_params.md">KSDS3D_ITD_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_ITD_PARAMS_MSG structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>