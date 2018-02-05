---
UID : NS:hdaudio._HDAUDIO_CODEC_RESPONSE
title : "_HDAUDIO_CODEC_RESPONSE"
author : windows-driver-content
description : The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.
old-location : audio\hdaudio_codec_response.htm
old-project : audio
ms.assetid : 56b9cdb5-2734-45b5-aeaf-ae6d606d1a5c
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : HDAUDIO_CODEC_RESPONSE, hdaudio/HDAUDIO_CODEC_RESPONSE, PHDAUDIO_CODEC_RESPONSE structure pointer [Audio Devices], aud-prop2_2cf51d01-4493-439c-9a5f-30b86d76502b.xml, hdaudio/PHDAUDIO_CODEC_RESPONSE, PHDAUDIO_CODEC_RESPONSE, audio.hdaudio_codec_response, _HDAUDIO_CODEC_RESPONSE, HDAUDIO_CODEC_RESPONSE structure [Audio Devices], *PHDAUDIO_CODEC_RESPONSE
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HDAUDIO_CODEC_RESPONSE, *PHDAUDIO_CODEC_RESPONSE
---

# _HDAUDIO_CODEC_RESPONSE structure
The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.

## Syntax
````
typedef struct _HDAUDIO_CODEC_RESPONSE {
  union {
    struct {
      union {
        struct {
          ULONG Response  :21;
          ULONG SubTag  :5;
          ULONG Tag  :4;
        } Unsolicited;
        ULONG  Response;
      };
      ULONG SDataIn  :4;
      ULONG IsUnsolicitedResponse  :1;
      ULONG   :25;
      ULONG HasFifoOverrun  :1;
      ULONG IsValid  :1;
    };
    ULONGLONG CompleteResponse;
  };
} HDAUDIO_CODEC_RESPONSE, *PHDAUDIO_CODEC_RESPONSE;
````

## Members


## Remarks
After calling the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine, function drivers can use the HDAUDIO_CODEC_RESPONSE structure to decode the responses to their codec commands. The commands are contained in the HDAUDIO_CODEC_TRANSFER structures that clients pass to this routine as call parameters.

The callback for the <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a> routine also uses the HDAUDIO_CODEC_RESPONSE structure.

Most members of this structure contain hardware-generated values that the bus driver copies directly from the corresponding RIRB entry. The two exceptions are the values of the <b>IsValid</b> and <b>HasFifoOverrun</b> members, which the bus driver software writes to the structure to indicate the error status of the response. For information about the RIRB entry format, see the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

If <b>IsValid</b>=0, one of the following has occurred:
<ul>
<li>
If <b>HasFifoOverrun</b>=1, the RIRB FIFO overflowed.

</li>
<li>
If <b>HasFifoOverrun</b>=0, the codec failed to respond.

</li>
</ul>The unnamed 25-bitfield between the <b>UnsolicitedResponse</b> and <b>HasFifoOverrun</b> members is reserved for future expansion. The HD Audio bus controller currently writes zeros to this field.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hdaudio.h (include Hdaudio.h) |

## See Also

<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_transfer.md">HDAUDIO_CODEC_TRANSFER</a>

<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_CODEC_RESPONSE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>