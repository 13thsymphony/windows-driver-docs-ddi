---
UID : NS:d3dumddi._DXVADDI_VIDEODESC
title : _DXVADDI_VIDEODESC
author : windows-driver-content
description : The DXVADDI_VIDEODESC structure describes a video stream.
old-location : display\dxvaddi_videodesc.htm
old-project : display
ms.assetid : 19121888-ad5c-4596-a7ec-a95fbffda685
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXVADDI_VIDEODESC, DXVADDI_VIDEODESC
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXVADDI_VIDEODESC
req.alt-loc : d3dumddi.h
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
req.typenames : DXVADDI_VIDEODESC
---

# _DXVADDI_VIDEODESC structure
The DXVADDI_VIDEODESC structure describes a video stream.

## Syntax
````
typedef struct _DXVADDI_VIDEODESC {
  UINT                   SampleWidth;
  UINT                   SampleHeight;
  DXVADDI_EXTENDEDFORMAT SampleFormat;
  D3DDDIFORMAT           Format;
  DXVADDI_FREQUENCY      InputSampleFreq;
  DXVADDI_FREQUENCY      OutputFrameFreq;
  UINT                   UABProtectionLevel;
  UINT                   Reserved;
} DXVADDI_VIDEODESC;
````

## Members

        
            `Format`

            [in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> structure that describes the extended format of the video sample.
        
            `InputSampleFreq`

            [in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_frequency.md">DXVADDI_FREQUENCY</a> structure that defines the frequency of incoming video.
        
            `OutputFrameFreq`

            [in] A DXVADDI_FREQUENCY structure that defines the frame rate of output video.
        
            `Reserved`

            [in] Reserved. Do not use this member.
        
            `SampleFormat`

            [in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure that describes the extended format of the video sample.
        
            `SampleHeight`

            [in] The height of the video sample, in pixels.
        
            `SampleWidth`

            [in] The width of the video sample, in pixels.
        
            `UABProtectionLevel`

            [in] A UINT value that specifies the level of data protection that is required when the user accessible bus is present.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_frequency.md">DXVADDI_FREQUENCY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEODESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>