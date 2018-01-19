---
UID : NS:ksmedia.KSDATAFORMAT_WAVEFORMATEX
title : KSDATAFORMAT_WAVEFORMATEX
author : windows-driver-content
description : The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data.
old-location : audio\ksdataformat_waveformatex.htm
old-project : audio
ms.assetid : b4c0cca8-6277-4458-b1f1-894848987074
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : KSDATAFORMAT_WAVEFORMATEX, KSDATAFORMAT_WAVEFORMATEX, *PKSDATAFORMAT_WAVEFORMATEX
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
req.alt-api : KSDATAFORMAT_WAVEFORMATEX
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
req.typenames : KSDATAFORMAT_WAVEFORMATEX, *PKSDATAFORMAT_WAVEFORMATEX
---

# KSDATAFORMAT_WAVEFORMATEX structure
The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data.

## Syntax
````
typedef struct {
  KSDATAFORMAT DataFormat;
  WAVEFORMATEX WaveFormatEx;
} KSDATAFORMAT_WAVEFORMATEX, *PKSDATAFORMAT_WAVEFORMATEX;
````

## Members

        
            `DataFormat`

            Specifies the general features of the stream's data format. This member is a structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff561656(v=vs.85).aspx">KSDATAFORMAT</a>.
        
            `WaveFormatEx`

            Describes the wave-specific details of the audio stream's data format. This member contains an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a> structure.

    ## Remarks
        In response to an input <i>DataRange</i> parameter that specifies a WAVEFORMATEX format (see example in <a href="https://msdn.microsoft.com/e8a9b681-3bd2-46ed-970f-5217dbfb2e4e">PCM Stream Data Range</a>), the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible WAVEFORMATEX format. If so, the method outputs a KSDATAFORMAT_WAVEFORMATEX structure (see example in <a href="https://msdn.microsoft.com/86599e55-e771-4d6e-ad59-6dc905c53cd8">PCM Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.

Note that the <b>WaveFormatEx</b> member of the KSDATAFORMAT_WAVEFORMATEX structure can be extended to include additional format information (for example, a channel configuration mask). For more information, see <a href="..\ksmedia\ns-ksmedia-waveformatextensible.md">WAVEFORMATEXTENSIBLE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

    ## See Also

        <dl>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff561656(v=vs.85).aspx">KSDATAFORMAT</a></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-waveformatextensible.md">WAVEFORMATEXTENSIBLE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDATAFORMAT_WAVEFORMATEX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>