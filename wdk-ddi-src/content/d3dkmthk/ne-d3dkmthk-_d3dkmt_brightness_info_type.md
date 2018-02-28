---
UID: NE:d3dkmthk._D3DKMT_BRIGHTNESS_INFO_TYPE
title: "_D3DKMT_BRIGHTNESS_INFO_TYPE"
author: windows-driver-content
description: Indicates the type of information to retrieve or set for the brightness of an integrated display panel.
old-location: display\d3dkmt_brightness_info_type.htm
old-project: display
ms.assetid: 0f37ac57-9f3b-4bbc-a927-ea85aa44f910
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_BRIGHTNESS_INFO_BEGIN_MANUAL_MODE, D3DKMT_BRIGHTNESS_INFO_END_MANUAL_MODE, D3DKMT_BRIGHTNESS_INFO_GET, D3DKMT_BRIGHTNESS_INFO_GET_CAPS, D3DKMT_BRIGHTNESS_INFO_GET_POSSIBLE_LEVELS, D3DKMT_BRIGHTNESS_INFO_GET_REDUCTION, D3DKMT_BRIGHTNESS_INFO_SET, D3DKMT_BRIGHTNESS_INFO_SET_OPTIMIZATION, D3DKMT_BRIGHTNESS_INFO_SET_STATE, D3DKMT_BRIGHTNESS_INFO_TOGGLE_LOGGING, D3DKMT_BRIGHTNESS_INFO_TYPE, D3DKMT_BRIGHTNESS_INFO_TYPE enumeration [Display Devices], _D3DKMT_BRIGHTNESS_INFO_TYPE, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_BEGIN_MANUAL_MODE, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_END_MANUAL_MODE, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_GET, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_GET_CAPS, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_GET_POSSIBLE_LEVELS, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_GET_REDUCTION, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_SET, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_SET_OPTIMIZATION, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_SET_STATE, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_TOGGLE_LOGGING, d3dkmthk/D3DKMT_BRIGHTNESS_INFO_TYPE, display.d3dkmt_brightness_info_type
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_BRIGHTNESS_INFO_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_BRIGHTNESS_INFO_TYPE
---

# _D3DKMT_BRIGHTNESS_INFO_TYPE Enumeration
Indicates the type of information to retrieve or set for the brightness of an integrated display panel.

## Syntax
````
typedef enum _D3DKMT_BRIGHTNESS_INFO_TYPE { 
  D3DKMT_BRIGHTNESS_INFO_GET_POSSIBLE_LEVELS  = 1,
  D3DKMT_BRIGHTNESS_INFO_GET                  = 2,
  D3DKMT_BRIGHTNESS_INFO_SET                  = 3,
  D3DKMT_BRIGHTNESS_INFO_GET_CAPS             = 4,
  D3DKMT_BRIGHTNESS_INFO_SET_STATE            = 5,
  D3DKMT_BRIGHTNESS_INFO_SET_OPTIMIZATION     = 6,
  D3DKMT_BRIGHTNESS_INFO_GET_REDUCTION        = 7,
  D3DKMT_BRIGHTNESS_INFO_BEGIN_MANUAL_MODE    = 8,
  D3DKMT_BRIGHTNESS_INFO_END_MANUAL_MODE      = 9,
  D3DKMT_BRIGHTNESS_INFO_TOGGLE_LOGGING       = 10
} D3DKMT_BRIGHTNESS_INFO_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_BEGIN_MANUAL_MODE</td>
                    <td>The user has begun to manually adjust the brightness level.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_END_MANUAL_MODE</td>
                    <td>The user has ended the manual adjustment of the brightness level.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_GET</td>
                    <td>Retrieve the currently active brightness level.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_GET_CAPS</td>
                    <td>Retrieve brightness control capabilities of the integrated display panel.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_GET_POSSIBLE_LEVELS</td>
                    <td>Retrieve all possible brightness levels that the integrated display panel supports.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_GET_REDUCTION</td>
                    <td>Retrieve the current level of backlight reduction that is applied to the integrated display panel.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_SET</td>
                    <td>Set a new brightness level.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_SET_OPTIMIZATION</td>
                    <td>Set the level of optimization that the display miniport driver uses to control the brightness of the integrated display panel.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_SET_STATE</td>
                    <td>Enable smooth brightness control.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_BRIGHTNESS_INFO_TOGGLE_LOGGING</td>
                    <td>Enable or disable Event Tracing for Windows (ETW) logging of brightness information.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |