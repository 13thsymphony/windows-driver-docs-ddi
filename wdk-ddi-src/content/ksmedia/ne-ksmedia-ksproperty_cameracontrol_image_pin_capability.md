---
UID: NE:ksmedia.KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
title: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
author: windows-driver-content
description: Used to identify whether the camera's image pin and record pin are mutually exclusive. If they are mutually exclusive, then when the record pin is active, the image pin cannot be active, and vice-versa.
old-location: stream\ksproperty_cameracontrol_image_pin_capability.htm
old-project: stream
ms.assetid: FB7FB950-079C-41DC-AB9D-AD5D7460D7A7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY enumeration [Streaming Media Devices], KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY_ID, ksmedia/KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY, ksmedia/KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY_ID, stream.ksproperty_cameracontrol_image_pin_capability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
---

# KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY Enumeration
Used to identify whether the camera's image pin and record pin are mutually exclusive. If they are mutually exclusive, then when the record pin is active, the image pin cannot be active, and vice-versa.

## Syntax
````
typedef enum _KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY { 
  KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY_ID  = 0
} KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY;
````

## Constants

<table>
            
                <tr>
                    <td>KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY_ID</td>
                    <td>The <a href="https://msdn.microsoft.com/library/windows/hardware/jj553706">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY</a> property is used to identify whether the camera's image pin and the record pin are mutually exclusive.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj553706">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY</a>