---
UID: NC.dispmprt.DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2
title: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2
author: windows-driver-content
description: Called by a display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running Windows Display Driver Model (WDDM) driver.
old-location: display\dxgkcb_acquire_post_display_ownership2.htm
old-project: display
ms.assetid: 923A2107-8F5E-4EF7-8C3C-4EFDE26A50F5
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, PSYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkcbAcquirePostDisplayOwnership2
req.alt-loc: dispmprt.h
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
---

# DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2 callback



## -description
Called by a display miniport driver to obtain the display information from the current  power-on self-test (POST) display device or the previously running Windows Display Driver Model (WDDM) driver.



## -prototype

````
DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2 DxgkcbAcquirePostDisplayOwnership2;

NTSTATUS DxgkcbAcquirePostDisplayOwnership2(
   HANDLE                        DeviceHandle,
   PDXGK_DISPLAY_INFORMATION     DisplayInfo,
   PDXGK_DISPLAY_OWNERSHIP_FLAGS Flags
)
{ ... }

typedef DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2 ;
````


## -parameters

### -param DeviceHandle 

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the  member of the DXGKRNL_INTERFACE structure that was passed to DxgkDdiStartDevice.


### -param DisplayInfo 

A pointer to a DXGK_DISPLAY_INFORMATION structure that is allocated by the display miniport driver. If DxgkCbAcquirePostDisplayOwnership returns STATUS_SUCCESS, this structure contains display information for the current display device that is used for POST operations.


### -param Flags 

A pointer to a DXGK_DISPLAY_OWNERSHIP_FLAGS structure that is allocated by the display miniport driver. If DxgkCbAcquirePostDisplayOwnership2 returns STATUS_SUCCESS, this structure contains flags in bit fields describing the ownership of the display.  The only bit fields defined in WDDM 2.2 contain a DXGK_FRAMEBUFFER_STATE enum indicating how the frame buffer was initialized.


## -returns

<a href="display.DxgkCbAcquirePostDisplayOwnership">DxgkCbAcquirePostDisplayOwnership</a> returns STATUS_SUCCESS if it succeeds. 


## -remarks
Register your implementation of this callback function by setting the appropriate member of  and then calling .


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h</dt>
</dl>
</td>
</tr>
</table>