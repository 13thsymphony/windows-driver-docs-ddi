---
UID : NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
title : KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
author : windows-driver-content
description : The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface.
old-location : stream\ksproperty_allocator_control_surface_size_s.htm
old-project : stream
ms.assetid : 2ed72182-b098-43a6-a327-a8d81ab66309
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
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
req.alt-api : KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
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
req.typenames : KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure
The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface.

## Syntax
````
typedef struct {
  ULONG CX;
  ULONG CY;
} KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S;
````

## Members

        
            `CX`

            Specifies the width of the overlay surface.
        
            `CY`

            Specifies the height of the overlay surface


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564278">KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>