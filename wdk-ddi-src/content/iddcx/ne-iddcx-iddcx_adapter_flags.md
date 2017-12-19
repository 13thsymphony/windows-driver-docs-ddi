---
UID: NE.iddcx.IDDCX_ADAPTER_FLAGS
title: IDDCX_ADAPTER_FLAGS
author: windows-driver-content
description: Specifies boolean flags for an indirect display adapter.
old-location: display\iddcx_adapter_flags.htm
old-project: display
ms.assetid: 832ca4fe-1040-4f07-8c84-f576e5ce6423
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDDCX_ADAPTER_FLAGS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDDCX_ADAPTER_FLAGS
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
---

# IDDCX_ADAPTER_FLAGS enumeration



## -description

                    Specifies boolean flags for an indirect display adapter.
                



## -syntax

````
typedef enum _IDDCX_ADAPTER_FLAGS { 
  IDDCX_ADAPTER_FLAGS_NONE                  = 0,
  IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE     = 1,
  IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS  = 2
} IDDCX_ADAPTER_FLAGS;
````


## -enum-fields

### -field IDDCX_ADAPTER_FLAGS_NONE


                        
                    Indicates that there are no flags set for the adapter.


### -field IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE


                        Indicates to the OS that the smallest possible desktop surface size should be used when the desktop mode is changed. Typically a solution that has a large processing overhead or limited transmission bandwidth uses this flag to reduce the desktop image size in order to process as much as possible. 

<div class="alert"><b>Note</b>  Setting this flag results in a mode change each time the desktop resolution is changed.</div>
<div> </div>

### -field IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS


                        Indicates if the driver can utilize move regions provided by the OS in addition to dirty rects when encoding the image.  The driver should only set this to TRUE if it uses the move regions because  this costs additional resource for the OS to generate them. If driver sets this to FALSE, the OS converts all move regions to dirty rects.
                    


## -remarks
Indirect display automatically supports OS virtual modes.  Mode changes can be performed seamlessly by the OS using DWM scaling on a per frame basis without any display mode change. The disadvantage of this is that when a smaller desktop mode is used by the user, the desktop image provided to the driver will be bigger than the desktop size. 		This wastes encode and transmit bandwidth. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>