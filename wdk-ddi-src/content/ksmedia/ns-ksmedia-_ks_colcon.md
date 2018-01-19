---
UID : NS:ksmedia._KS_COLCON
title : _KS_COLCON
author : windows-driver-content
description : The KS_COLCON structure is used to describe color and contrast settings.
old-location : stream\ks_colcon.htm
old-project : stream
ms.assetid : 8328c1b1-e72d-4e34-b69e-e02b3f5850bf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _KS_COLCON, KS_COLCON, *PKS_COLCON
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
req.alt-api : KS_COLCON
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
req.typenames : KS_COLCON, *PKS_COLCON
---

# _KS_COLCON structure
The KS_COLCON structure is used to describe color and contrast settings.

## Syntax
````
typedef struct _KS_COLCON {
  UCHAR emph1col  :4;
  UCHAR emph2col  :4;
  UCHAR backcol  :4;
  UCHAR patcol  :4;
  UCHAR emph1con  :4;
  UCHAR emph2con  :4;
  UCHAR backcon  :4;
  UCHAR patcon  :4;
} KS_COLCON, *PKS_COLCON;
````

## Members

        
            `backcol`

            Indicates
        
            `backcon`

            Indicates
        
            `emph1col`

            Indicates
        
            `emph1con`

            Indicates
        
            `emph2col`

            Indicates
        
            `emph2con`

            Indicates
        
            `patcol`

            Indicates
        
            `patcon`

            Indicates

    ## Remarks
        The KS_COLCON structure is used by the <a href="..\ksmedia\ns-ksmedia-_ksproperty_sphli.md">KSPROPERTY_SPHLI</a> structure.

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
<a href="..\ksmedia\ns-ksmedia-_ksproperty_sphli.md">KSPROPERTY_SPHLI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_COLCON structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>