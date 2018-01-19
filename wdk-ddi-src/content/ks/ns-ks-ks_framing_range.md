---
UID : NS:ks.KS_FRAMING_RANGE
title : KS_FRAMING_RANGE
author : windows-driver-content
description : The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.
old-location : stream\ks_framing_range.htm
old-project : stream
ms.assetid : 3263b290-2966-4e19-9828-b91e7b2efa55
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KS_FRAMING_RANGE, *PKS_FRAMING_RANGE, KS_FRAMING_RANGE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_FRAMING_RANGE
req.alt-loc : ks.h
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
req.typenames : "*PKS_FRAMING_RANGE, KS_FRAMING_RANGE"
---

# KS_FRAMING_RANGE structure
The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.

## Syntax
````
typedef struct {
  ULONG MinFrameSize;
  ULONG MaxFrameSize;
  ULONG Stepping;
} KS_FRAMING_RANGE, *PKS_FRAMING_RANGE;
````

## Members

        
            `MaxFrameSize`

            Specifies a maximum frame size of type ULONG.
        
            `MinFrameSize`

            Specifies a minimum frame size of type ULONG.
        
            `Stepping`

            Specifies the step value that should be used to create legal values within the range defined in <b>MinFrameSize</b> and <b>MaxFrameSize</b>.

    ## Remarks
        When specifying the <b>Stepping</b> member, ensure that the value does not exceed the difference between the <b>MinFrameSize</b> and <b>MaxFrameSize</b> members. Otherwise, unpredictable behavior may result.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ks_framing_item.md">KS_FRAMING_ITEM</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ks_framing_range_weighted.md">KS_FRAMING_RANGE_WEIGHTED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_FRAMING_RANGE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>