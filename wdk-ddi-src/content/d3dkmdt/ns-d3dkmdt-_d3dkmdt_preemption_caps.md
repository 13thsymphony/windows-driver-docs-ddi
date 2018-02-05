---
UID : NS:d3dkmdt._D3DKMDT_PREEMPTION_CAPS
title : "_D3DKMDT_PREEMPTION_CAPS"
author : windows-driver-content
description : Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.
old-location : display\d3dkmdt_preemption_caps.htm
old-project : display
ms.assetid : 52172edc-77a9-46b9-8382-c57c65b80b93
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMDT_PREEMPTION_CAPS, _D3DKMDT_PREEMPTION_CAPS, D3DKMDT_PREEMPTION_CAPS structure [Display Devices], display.d3dkmdt_preemption_caps, d3dkmdt/D3DKMDT_PREEMPTION_CAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMDT_PREEMPTION_CAPS
---

# _D3DKMDT_PREEMPTION_CAPS structure
Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.

## Syntax
````
typedef struct _D3DKMDT_PREEMPTION_CAPS {
  D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY GraphicsPreemptionGranularity;
  D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY  ComputePreemptionGranularity;
} D3DKMDT_PREEMPTION_CAPS;
````

## Members


`ComputePreemptionGranularity`

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_compute_preemption_granularity.md">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests that the driver can preempt for GPU compute shader operations.

`GraphicsPreemptionGranularity`

A  <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_graphics_preemption_granularity.md">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests  that the driver can preempt for GPU graphics  operations.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_graphics_preemption_granularity.md">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_compute_preemption_granularity.md">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_PREEMPTION_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>