---
UID: NS:d3dkmthk._D3DKMT_VIDPNSOURCEOWNER_FLAGS
title: "_D3DKMT_VIDPNSOURCEOWNER_FLAGS"
author: windows-driver-content
description: Specifies output duplication options for use with the D3DKMTSetVidPnSourceOwner1 function.
old-location: display\d3dkmt_vidpnsourceowner_flags.htm
old-project: display
ms.assetid: acc4e9d9-235f-4605-ae51-5056108843dc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DKMT_VIDPNSOURCEOWNER_FLAGS, D3DKMT_VIDPNSOURCEOWNER_FLAGS structure [Display Devices], D3DKMT_VIDPNSOURCEOWNER_FLAGS, d3dkmthk/D3DKMT_VIDPNSOURCEOWNER_FLAGS, display.d3dkmt_vidpnsourceowner_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
apiname:
-	D3DKMT_VIDPNSOURCEOWNER_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_VIDPNSOURCEOWNER_FLAGS
---

# _D3DKMT_VIDPNSOURCEOWNER_FLAGS structure
Specifies output duplication options for use with the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetvidpnsourceowner1.md">D3DKMTSetVidPnSourceOwner1</a> function.

## Syntax
````
typedef struct _D3DKMT_VIDPNSOURCEOWNER_FLAGS {
  union {
    struct {
      UINT AllowOutputDuplication  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DKMT_VIDPNSOURCEOWNER_FLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetvidpnsourceowner1.md">D3DKMTSetVidPnSourceOwner1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_VIDPNSOURCEOWNER_FLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>