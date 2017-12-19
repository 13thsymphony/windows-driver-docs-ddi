---
UID: NS.HDAUDIO._HDAUDIO_CODEC_RESPONSE
title: _HDAUDIO_CODEC_RESPONSE
author: windows-driver-content
description: The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.
old-location: audio\hdaudio_codec_response.htm
old-project: audio
ms.assetid: 56b9cdb5-2734-45b5-aeaf-ae6d606d1a5c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HDAUDIO_CODEC_RESPONSE, HDAUDIO_CODEC_RESPONSE, *PHDAUDIO_CODEC_RESPONSE, PHDAUDIO_CODEC_RESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_CODEC_RESPONSE
req.alt-loc: hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
---

# _HDAUDIO_CODEC_RESPONSE structure



## -description
The HDAUDIO_CODEC_RESPONSE structure specifies either a response to a codec command or an unsolicited response from a codec.



## -syntax

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


## -struct-fields

### -field ( unnamed struct )

Specifies a 26-bit unsolicited response value.


### -field Unsolicited

Specifies a 32-bit unsolicited response value that consists of a 26-bit response value and a 6-bit tag value.


### -field Response

Specifies a 26-bit unsolicited response value.


### -field Tag

Specifies a 6-bit tag value for an unsolicited response.

</dd>
</dl>

### -field Response

Specifies a 26-bit unsolicited response value.


### -field SDataIn

Specifies the 4-bit codec address (SDI line) of the codec that generates the response.


### -field IsUnsolicitedResponse

Specifies whether the response is unsolicited. If 1, the response is unsolicited. If 0, the response is solicited (that is, a response to a codec command).


### -field HasFifoOverrun

Specifies whether a FIFO overrun occurred in the response input ring buffer (RIRB). If 1, a FIFO overrun occurred. If 0, a FIFO overrun did not occur.


### -field IsValid

Specifies whether the response is valid. If 1, the response is valid. If 0, it is not valid.

</dd>
</dl>

### -field CompleteResponse

Specifies a complete, 64-bit response summary that consists of a 32-bit response, 4-bit codec address, three status bits, and 25 unused bits (set to zero). This value is mostly used in debug messages.


## -remarks
After calling the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine, function drivers can use the HDAUDIO_CODEC_RESPONSE structure to decode the responses to their codec commands. The commands are contained in the HDAUDIO_CODEC_TRANSFER structures that clients pass to this routine as call parameters.

The callback for the <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a> routine also uses the HDAUDIO_CODEC_RESPONSE structure.

Most members of this structure contain hardware-generated values that the bus driver copies directly from the corresponding RIRB entry. The two exceptions are the values of the <b>IsValid</b> and <b>HasFifoOverrun</b> members, which the bus driver software writes to the structure to indicate the error status of the response. For information about the RIRB entry format, see the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

If <b>IsValid</b>=0, one of the following has occurred:

If <b>HasFifoOverrun</b>=1, the RIRB FIFO overflowed.

If <b>HasFifoOverrun</b>=0, the codec failed to respond.

The unnamed 25-bitfield between the <b>UnsolicitedResponse</b> and <b>HasFifoOverrun</b> members is reserved for future expansion. The HD Audio bus controller currently writes zeros to this field.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>
</dt>
<dt>
<a href="audio.hdaudio_codec_transfer">HDAUDIO_CODEC_TRANSFER</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_CODEC_RESPONSE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

