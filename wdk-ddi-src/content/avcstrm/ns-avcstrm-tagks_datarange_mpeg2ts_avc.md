---
UID : NS:avcstrm.tagKS_DATARANGE_MPEG2TS_AVC
title : tagKS_DATARANGE_MPEG2TS_AVC
author : windows-driver-content
description : The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats.
old-location : stream\ks_datarange_mpeg2ts_avc.htm
old-project : stream
ms.assetid : 3e19439d-397c-4c22-823c-aa53c456d7b9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_DATARANGE_MPEG2TS_AVC, *PKS_DATARANGE_MPEG2TS_AVC, KS_DATARANGE_MPEG2TS_AVC
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : avcstrm.h
req.include-header : Avcstrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_DATARANGE_MPEG2TS_AVC
req.alt-loc : avcstrm.h
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
req.typenames : "*PKS_DATARANGE_MPEG2TS_AVC, KS_DATARANGE_MPEG2TS_AVC"
---

# tagKS_DATARANGE_MPEG2TS_AVC structure
The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats.

## Syntax
````
typedef struct tagKS_DATARANGE_MPEG2TS_AVC {
  KSDATARANGE       DataRange;
  AVCPRECONNECTINFO ConnectInfo;
} KS_DATARANGE_MPEG2TS_AVC, *PKS_DATARANGE_MPEG2TS_AVC;
````

## Members

        
            `ConnectInfo`

            Specifies the AV/C preconnection info.
        
            `DataRange`

            Specifies the range of supported AV/C MPEG2 formats.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | avcstrm.h (include Avcstrm.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>
</dt>
<dt>
<a href="..\avc\ns-avc-_avcpreconnectinfo.md">AVCPRECONNECTINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_MPEG2TS_AVC structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>