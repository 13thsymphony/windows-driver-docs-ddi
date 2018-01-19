---
UID : NS:ksmedia.SOUNDDETECTOR_PATTERNHEADER
title : SOUNDDETECTOR_PATTERNHEADER
author : windows-driver-content
description : The SOUNDDETECTOR_PATTERNHEADER structure specifies the pattern header for the sound detector in the KSPROPERTY_SOUNDDETECTOR_PATTERNS property.
old-location : audio\sounddetector_patternheader.htm
old-project : audio
ms.assetid : 43172627-2A05-44AD-8B39-8FC384F9F44E
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SOUNDDETECTOR_PATTERNHEADER, SOUNDDETECTOR_PATTERNHEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SOUNDDETECTOR_PATTERNHEADER
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
req.typenames : SOUNDDETECTOR_PATTERNHEADER
---

# SOUNDDETECTOR_PATTERNHEADER structure
The <b>SOUNDDETECTOR_PATTERNHEADER</b> structure specifies the pattern header for the sound detector in the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn932151">KSPROPERTY_SOUNDDETECTOR_PATTERNS</a> property.

## Syntax
````
typedef struct {
  ULONG Size;
  GUID  PatternType;
} SOUNDDETECTOR_PATTERNHEADER;
````

## Members

        
            `PatternType`

            The keyword pattern format, expressed as a GUID.
        
            `Size`

            The size of the audio data.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn932151">KSPROPERTY_SOUNDDETECTOR_PATTERNS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SOUNDDETECTOR_PATTERNHEADER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>