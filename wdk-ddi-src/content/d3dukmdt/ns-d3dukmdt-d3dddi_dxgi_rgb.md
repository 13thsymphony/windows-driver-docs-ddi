---
UID : NS:d3dukmdt.D3DDDI_DXGI_RGB
title : D3DDDI_DXGI_RGB
author : windows-driver-content
description : The D3DDDI_DXGI_RGB structure contains information to describe a gamma function.
old-location : display\d3dddi_dxgi_rgb.htm
old-project : display
ms.assetid : 4bf25ae0-30fa-49a6-a5a8-c807e14d9857
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DDDI_DXGI_RGB, D3DDDI_DXGI_RGB
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dukmdt.h
req.include-header : D3dukmdt.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDI_DXGI_RGB
req.alt-loc : d3dukmdt.h
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
req.typenames : D3DDDI_DXGI_RGB
---

# D3DDDI_DXGI_RGB structure
The D3DDDI_DXGI_RGB structure contains information to describe a gamma function.

## Syntax
````
typedef struct D3DDDI_DXGI_RGB {
  float Red;
  float Green;
  float Blue;
} D3DDDI_DXGI_RGB;
````

## Members

        
            `Blue`

            A FLOAT value that is used to describe the gamma function for the blue color channel.
        
            `Green`

            A FLOAT value that is used to describe the gamma function for the green color channel.
        
            `Red`

            A FLOAT value that is used to describe the gamma function for the red color channel.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md">D3DDDI_GAMMA_RAMP_DXGI_1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_DXGI_RGB structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>