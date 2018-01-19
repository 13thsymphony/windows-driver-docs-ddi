---
UID : NS:ksmedia.tagKS_VIDEOINFO
title : tagKS_VIDEOINFO
author : windows-driver-content
description : The KS_VIDEOINFO structure describes the bitmap and color information for a video stream.
old-location : stream\ks_videoinfo.htm
old-project : stream
ms.assetid : e588a844-0b20-418c-9c65-e85f3a992d5c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_VIDEOINFO, *PKS_VIDEOINFO, KS_VIDEOINFO
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
req.alt-api : KS_VIDEOINFO
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
req.typenames : "*PKS_VIDEOINFO, KS_VIDEOINFO"
---

# tagKS_VIDEOINFO structure
The KS_VIDEOINFO structure describes the bitmap and color information for a video stream.

## Syntax
````
typedef struct tagKS_VIDEOINFO {
  RECT                rcSource;
  RECT                rcTarget;
  DWORD               dwBitRate;
  DWORD               dwBitErrorRate;
  REFERENCE_TIME      AvgTimePerFrame;
  KS_BITMAPINFOHEADER bmiHeader;
  union {
    KS_RGBQUAD       bmiColors[KS_iPALETTE_COLORS];
    DWORD            dwBitMasks[KS_iMASK_COLORS];
    KS_TRUECOLORINFO TrueColorInfo;
  };
} KS_VIDEOINFO, *PKS_VIDEOINFO;
````

## Members

        
            `AvgTimePerFrame`

            Specifies the average time per frame in 100-nanosecond units.
        
            `bmiHeader`

            Describes a <a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a> structure that contains color and dimension information about the video image bitmap.
        
            `dwBitErrorRate`

            Specifies a value that indicates the video stream's data error rate, in bit errors per second.
        
            `dwBitRate`

            Specifies a value that indicates the video stream's approximate data rate, in bits per second.
        
            `rcSource`

            Specifies a clipping rectangle that selects the portion of the active video signal to use.
        
            `rcTarget`

            Specifies a rectangle that indicates which part of the target buffer to use.

    ## Remarks
        This structure must not be used unless the <b>biSize</b> member of the KS_BITMAPINFOHEADER member is set to <b>sizeof</b>(KS_BITMAPINFOHEADER).

A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the <b>rcSource</b> member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks <b>rcSource</b> and if the sink filter does not support image extraction and the rectangle is <i>not</i> empty, then it rejects the connection. A filter should use the Win32 function <b>SetRectEmpty</b> to reset a rectangle to all zeros (and <b>IsRectEmpty</b> to later check the rectangle).

The <b>rcTarget</b> member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers it supplies. In this case, it calls the Win32 function <b>QueryAccept</b> with a nonempty target.

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
<a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_rgbquad.md">KS_RGBQUAD</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tag_ks_truecolorinfo.md">KS_TRUECOLORINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VIDEOINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>