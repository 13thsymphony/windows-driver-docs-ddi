---
UID: NS:d3dkmthk._D3DKMT_VIDSCH_ESCAPE
title: "_D3DKMT_VIDSCH_ESCAPE"
author: windows-driver-content
description: The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_vidsch_escape.htm
old-project: display
ms.assetid: 8e19e8a1-0cb6-4d57-862c-2e3a785b949b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dkmthk/D3DKMT_VIDSCH_ESCAPE, _D3DKMT_VIDSCH_ESCAPE, display.d3dkmt_vidsch_escape, D3DKMT_VIDSCH_ESCAPE, D3DKMT_VIDSCH_ESCAPE structure [Display Devices], OpenGL_Structs_d668addb-7c4a-4f07-bf9b-71ccd4a216fa.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_VIDSCH_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_VIDSCH_ESCAPE
---

# _D3DKMT_VIDSCH_ESCAPE structure
<b>Do not use the D3DKMT_VIDSCH_ESCAPE structure; it is for testing purposes only.</b>

The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.

## Syntax
````
typedef struct _D3DKMT_VIDSCH_ESCAPE {
  D3DKMT_VIDSCHESCAPETYPE Type;
  union {
    BOOL   PreemptionControl;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    BOOL   EnableContextDelay;
    struct {
      ULONG TdrControl;
      union {
        ULONG NodeOrdinal;
      };
    } TdrControl2;
#endif 
    BOOL   SuspendScheduler;
    ULONG  TdrControl;
    ULONG  SuspendTime;
  };
} D3DKMT_VIDSCH_ESCAPE;
````

## Members


`Type`

The escape type, of type <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_vidschescapetype.md">D3DKMT_VIDSCHESCAPETYPE</a>, which is reserved and should not be used in your driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_vidschescapetype.md">D3DKMT_VIDSCHESCAPETYPE</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_VIDSCH_ESCAPE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>