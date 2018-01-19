---
UID : NS:dispmprt._DXGK_MIRACAST_CAPS
title : _DXGK_MIRACAST_CAPS
author : windows-driver-content
description : Used by a display miniport driver to identify capabilities of a Miracast device.
old-location : display\dxgk_miracast_caps.htm
old-project : display
ms.assetid : 63ED28D9-654F-45CC-BFDC-89C9E73DCF95
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_MIRACAST_CAPS, DXGK_MIRACAST_CAPS, *PDXGK_MIRACAST_CAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_MIRACAST_CAPS
req.alt-loc : Dispmprt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DXGK_MIRACAST_CAPS, *PDXGK_MIRACAST_CAPS
---

# _DXGK_MIRACAST_CAPS structure
Used by a display miniport driver to identify capabilities of a Miracast device.

## Syntax
````
typedef struct _DXGK_MIRACAST_CAPS {
  ULONG MaxChunkPrivateDriverDataSize;
  union {
    struct {
      UINT HdcpSupport  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  } Flags;
} DXGK_MIRACAST_CAPS, *PDXGK_MIRACAST_CAPS;
````

## Members

        
            `Flags`

            
        
            `MaxChunkPrivateDriverDataSize`

            The maximum size, in bytes, of the private data that the display miniport driver will pass when it reports a <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a> interrupt type of <b>DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h (include Dispmprt.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MIRACAST_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>