---
UID : NS:ksmedia.tagKS_TVTUNER_CHANGE_INFO
title : tagKS_TVTUNER_CHANGE_INFO
author : windows-driver-content
description : The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.
old-location : stream\ks_tvtuner_change_info.htm
old-project : stream
ms.assetid : 7bb04fbb-2894-4148-88c2-fbbebb000ec9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_TVTUNER_CHANGE_INFO, KS_TVTUNER_CHANGE_INFO, *PKS_TVTUNER_CHANGE_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_TVTUNER_CHANGE_INFO
req.alt-loc : ksmedia.h
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
req.typenames : KS_TVTUNER_CHANGE_INFO, *PKS_TVTUNER_CHANGE_INFO
---

# tagKS_TVTUNER_CHANGE_INFO structure
The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.

## Syntax
````
typedef struct tagKS_TVTUNER_CHANGE_INFO {
  DWORD dwFlags;
  DWORD dwCountryCode;
  DWORD dwAnalogVideoStandard;
  DWORD dwChannel;
} KS_TVTUNER_CHANGE_INFO, *PKS_TVTUNER_CHANGE_INFO;
````

## Members

        
            `dwAnalogVideoStandard`

            Specifies the current analog video standard. This member should be set to a value from the <a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a> enumeration.
        
            `dwChannel`

            Specifies the current channel number.
        
            `dwCountryCode`

            Specifies the country code in use. This corresponds to the International Telecommunications Unit (ITU) long distance dialing code.
        
            `dwFlags`

            Specifies flags indicating the status of the tuning operation. This member must be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_TVTUNER_CHANGE_BEGIN_TUNE

</td>
<td>
Indicates that a tuning operation has begun. VBI codecs should stop decoding at this time, because the video signal may become corrupted.

</td>
</tr>
<tr>
<td>
KS_TVTUNER_CHANGE_END_TUNE

</td>
<td>
Indicates completion of a tuning operation. VBI codecs should resume decoding.

</td>
</tr>
</table>

    ## Remarks
        A packet containing a KS_TVTUNER_CHANGE_INFO structure normally originates at a TV tuner filter, and is propagated through any crossbars to an analog video decoder capture filter. The capture filter in turn must propagate this packet to downstream VBI codecs as part of a VBI media sample.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_TVTUNER_CHANGE_INFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>