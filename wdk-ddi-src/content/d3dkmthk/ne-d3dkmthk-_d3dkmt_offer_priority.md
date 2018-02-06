---
UID: NE:d3dkmthk._D3DKMT_OFFER_PRIORITY
title: "_D3DKMT_OFFER_PRIORITY"
author: windows-driver-content
description: Indicates the importance of video memory resources that the user-mode display driver offers for reuse.
old-location: display\d3dkmt_offer_priority.htm
old-project: display
ms.assetid: fec15098-3130-42d6-b889-579ecab6f162
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_OFFER_PRIORITY_LOW, d3dkmthk/D3DKMT_OFFER_PRIORITY_HIGH, D3DKMT_OFFER_PRIORITY, D3DKMT_OFFER_PRIORITY enumeration [Display Devices], d3dkmthk/D3DKMT_OFFER_PRIORITY_NORMAL, d3dkmthk/D3DKMT_OFFER_PRIORITY_LOW, display.d3dkmt_offer_priority, D3DKMT_OFFER_PRIORITY_HIGH, d3dkmthk/D3DKMT_OFFER_PRIORITY_AUTO, _D3DKMT_OFFER_PRIORITY, d3dkmthk/D3DKMT_OFFER_PRIORITY, D3DKMT_OFFER_PRIORITY_NORMAL, D3DKMT_OFFER_PRIORITY_AUTO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3DKMT_OFFER_PRIORITY
product: Windows
targetos: Windows
req.typenames: D3DKMT_OFFER_PRIORITY
---

# _D3DKMT_OFFER_PRIORITY Enumeration
Indicates the importance of video memory resources  that the user-mode display driver offers for reuse.

## Syntax
````
typedef enum _D3DKMT_OFFER_PRIORITY { 
  D3DKMT_OFFER_PRIORITY_LOW     = 1,
  D3DKMT_OFFER_PRIORITY_NORMAL  = 2,
  D3DKMT_OFFER_PRIORITY_HIGH    = 3,
  D3DKMT_OFFER_PRIORITY_AUTO    = 4
} D3DKMT_OFFER_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMT_OFFER_PRIORITY_AUTO</td>
                    <td>The video memory manager should make a policy decision on the allocation's value based on its  priority for eviction.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_OFFER_PRIORITY_HIGH</td>
                    <td>The allocation has useful content and cannot easily be regenerated. The video memory manager (which is part of Dxgkrnl.sys) should therefore avoid discarding this allocation before other offered allocations.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_OFFER_PRIORITY_LOW</td>
                    <td>The allocation has low value and should be discarded before other offered allocations. Specify this type for allocations that have no useful content.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_OFFER_PRIORITY_NORMAL</td>
                    <td>The allocation has useful content but can easily be regenerated.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

    ## See Also

        <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_offerallocations.md">D3DKMT_OFFERALLOCATIONS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OFFER_PRIORITY enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>