---
UID : NS:avcstrm.tagKS_DATAFORMAT_MPEG2TS_AVC
title : tagKS_DATAFORMAT_MPEG2TS_AVC
author : windows-driver-content
description : The KS_DATAFORMAT_MPEG2TS_AVC structure stores the data format for an AV/C MPEG2 connection.
old-location : stream\ks_dataformat_mpeg2ts_avc.htm
old-project : stream
ms.assetid : 17768308-d92d-4033-aee8-2d52ce1e51fd
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_DATAFORMAT_MPEG2TS_AVC, *PKS_DATAFORMAT_MPEG2TS_AVC, KS_DATAFORMAT_MPEG2TS_AVC
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
req.alt-api : KS_DATAFORMAT_MPEG2TS_AVC
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
req.typenames : "*PKS_DATAFORMAT_MPEG2TS_AVC, KS_DATAFORMAT_MPEG2TS_AVC"
---

# tagKS_DATAFORMAT_MPEG2TS_AVC structure
The KS_DATAFORMAT_MPEG2TS_AVC structure stores the data format for an AV/C MPEG2 connection.

## Syntax
````
typedef struct tagKS_DATAFORMAT_MPEG2TS_AVC {
  KSDATAFORMAT   DataFormat;
  AVCCONNECTINFO ConnectInfo;
} KS_DATAFORMAT_MPEG2TS_AVC, *PKS_DATAFORMAT_MPEG2TS_AVC;
````

## Members

        
            `ConnectInfo`

            Specifies the AV/C connection information.
        
            `DataFormat`

            Specifies the data format of the MPEG2 connection.


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
<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>
</dt>
<dt>
<a href="..\avc\ns-avc-_avcconnectinfo.md">AVCCONNECTINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_MPEG2TS_AVC structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>