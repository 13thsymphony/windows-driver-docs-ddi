---
UID: NE:umdprovider._UMDETW_ALLOCATION_SEMANTIC
title: "_UMDETW_ALLOCATION_SEMANTIC"
author: windows-driver-content
description: Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.
old-location: display\umdetw_allocation_semantic.htm
old-project: display
ms.assetid: 4c0fa5c1-7d73-4380-a673-f09bbf0ea281
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.umdetw_allocation_semantic, umdprovider/UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING, UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE, umdprovider/UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER, umdprovider/UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING, UMDETW_ALLOCATION_SEMANTIC enumeration [Display Devices], umdprovider/UMDETW_ALLOCATION_SEMANTIC_NONE, UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX, umdprovider/UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX, UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING, UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING, _UMDETW_ALLOCATION_SEMANTIC, UMDETW_ALLOCATION_SEMANTIC, umdprovider/UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN, UMDETW_ALLOCATION_SEMANTIC_NONE, umdprovider/UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE, umdprovider/UMDETW_ALLOCATION_SEMANTIC, UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER, UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: umdprovider.h
req.include-header: Umdprovider.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	umdprovider.h
apiname:
-	UMDETW_ALLOCATION_SEMANTIC
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_SEMANTIC
req.product: Windows 10 or later.
---

# _UMDETW_ALLOCATION_SEMANTIC Enumeration
Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.

## Syntax
````
typedef enum _UMDETW_ALLOCATION_SEMANTIC { 
  UMDETW_ALLOCATION_SEMANTIC_NONE              = 0,
  UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER        = 1,
  UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING    = 2,
  UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING  = 3,
  UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE      = 4,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN  = 5,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX  = 0xFFFF
} UMDETW_ALLOCATION_SEMANTIC;
````

## Constants

<table>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE</td>
                    <td>The allocation is used as a GPU context save area.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER</td>
                    <td>The allocation is used as a DMA buffer.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING</td>
                    <td>The allocation is used exclusively as a staging allocation to download data from video memory.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX</td>
                    <td>The driver can use this semantic value for its own internal purposes.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN</td>
                    <td>The driver can use this semantic value for its own internal purposes.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_NONE</td>
                    <td>The allocation is created for a Direct3D resource.</td>
                </tr>
            
                <tr>
                    <td>UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING</td>
                    <td>The allocation is used as a staging allocation to upload and download data to and from video memory.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | umdprovider.h (include Umdprovider.h) |

    ## See Also

        <a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>



<a href="..\umdprovider\nf-umdprovider-umdetwlogunmapallocation.md">UMDEtwLogUnmapAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDETW_ALLOCATION_SEMANTIC enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>