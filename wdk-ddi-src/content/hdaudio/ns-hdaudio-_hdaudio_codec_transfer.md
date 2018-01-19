---
UID : NS:hdaudio._HDAUDIO_CODEC_TRANSFER
title : _HDAUDIO_CODEC_TRANSFER
author : windows-driver-content
description : The HDAUDIO_CODEC_TRANSFER structure specifies a codec command and the response to that command.
old-location : audio\hdaudio_codec_transfer.htm
old-project : audio
ms.assetid : ee73c5d2-9c4d-4d6f-b792-7966964fedf7
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _HDAUDIO_CODEC_TRANSFER, *PHDAUDIO_CODEC_TRANSFER, HDAUDIO_CODEC_TRANSFER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hdaudio.h
req.include-header : Hdaudio.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HDAUDIO_CODEC_TRANSFER
req.alt-loc : hdaudio.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL.
req.typenames : "*PHDAUDIO_CODEC_TRANSFER, HDAUDIO_CODEC_TRANSFER"
---

# _HDAUDIO_CODEC_TRANSFER structure
The HDAUDIO_CODEC_TRANSFER structure specifies a codec command and the response to that command.

## Syntax
````
typedef struct _HDAUDIO_CODEC_TRANSFER {
  HDAUDIO_CODEC_COMMAND  Output;
  HDAUDIO_CODEC_RESPONSE Input;
} HDAUDIO_CODEC_TRANSFER, *PHDAUDIO_CODEC_TRANSFER;
````

## Members

        
            `Input`

            Specifies the response to the codec command. This member is a structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md">HDAUDIO_CODEC_RESPONSE</a>. The HD Audio bus driver retrieves the response to the codec command that is contained in the <b>Output</b> member and writes the response into the <b>Input</b> member.
        
            `Output`

            Specifies a codec command for the HD Audio bus driver to output to a codec that is attached to the HD Audio controller. This member is a structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_command.md">HDAUDIO_CODEC_COMMAND</a>. Before calling the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine, the caller writes a codec command to this member.

    ## Remarks
        This structure is used by the <b>TransferCodecVerbs</b> routine:

At entry, the <b>Output</b> member contains a codec command from the caller.

Upon return, the <b>Input</b> member contains the response to the codec command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hdaudio.h (include Hdaudio.h) |

    ## See Also

        <dl>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_command.md">HDAUDIO_CODEC_COMMAND</a>
</dt>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md">HDAUDIO_CODEC_RESPONSE</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_CODEC_TRANSFER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>