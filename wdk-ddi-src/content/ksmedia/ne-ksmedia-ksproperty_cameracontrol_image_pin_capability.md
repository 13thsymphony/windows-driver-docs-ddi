---
UID : NE:ksmedia.KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
title : KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
author : windows-driver-content
description : Used to identify whether the camera's image pin and record pin are mutually exclusive. If they are mutually exclusive, then when the record pin is active, the image pin cannot be active, and vice-versa.
old-location : stream\ksproperty_cameracontrol_image_pin_capability.htm
old-project : stream
ms.assetid : FB7FB950-079C-41DC-AB9D-AD5D7460D7A7
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
req.alt-loc : Ksmedia.h
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
req.typenames : KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj553706">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>