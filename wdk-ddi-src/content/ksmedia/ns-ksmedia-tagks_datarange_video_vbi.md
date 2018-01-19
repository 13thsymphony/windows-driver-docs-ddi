---
UID : NS:ksmedia.tagKS_DATARANGE_VIDEO_VBI
title : tagKS_DATARANGE_VIDEO_VBI
author : windows-driver-content
description : The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.
old-location : stream\ks_datarange_video_vbi.htm
old-project : stream
ms.assetid : 83801ea2-1beb-4b73-8906-ffefee67a2ac
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_DATARANGE_VIDEO_VBI, KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI
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
req.alt-api : KS_DATARANGE_VIDEO_VBI
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
req.typenames : KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI
---

# tagKS_DATARANGE_VIDEO_VBI structure
The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.

## Syntax
````
typedef struct tagKS_DATARANGE_VIDEO_VBI {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_VBIINFOHEADER            VBIInfoHeader;
} KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI;
````

## Members

        
            `bFixedSizeSamples`

            Specifies that all the samples are the same size if set to <b>TRUE</b>.
        
            `bTemporalCompression`

            Specifies whether each sample can stand independently on its own, without relying on previous or future samples.
        
            `ConfigCaps`

            Specifies the configuration of the stream, including scaling, cropping, and frame and data rates.
        
            `DataRange`

            Specifies major, minor, and specifier identifiers of the range of formats being described.
        
            `MemoryAllocationFlags`

            Unused and should be set to zero.
        
            `StreamDescriptionFlags`

            Unused and should be set to zero.
        
            `VBIInfoHeader`

            Indicates VBI-specific information for the range of formats being described.


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
<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_vbiinfoheader.md">KS_VBIINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_VIDEO_VBI structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>