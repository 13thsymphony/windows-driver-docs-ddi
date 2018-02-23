---
UID: NE:wwan._WWAN_VOICE_CLASS
title: "_WWAN_VOICE_CLASS"
author: windows-driver-content
description: The WWAN_VOICE_CLASS enumeration lists the different types of voice classes that are supported by the MB device.
old-location: netvista\wwan_voice_class.htm
old-project: netvista
ms.assetid: 288a7b44-b842-41f8-8ece-d14a709b0717
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wwan_voice_class, WwanVoiceClassMax, PWWAN_VOICE_CLASS, WwanVoiceClassUnknown, WwanVoiceClassSeparateVoiceData, WwanVoiceClassSimultaneousVoiceData, PWWAN_VOICE_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], _WWAN_VOICE_CLASS, wwan/WwanVoiceClassUnknown, WWAN_VOICE_CLASS, wwan/PWWAN_VOICE_CLASS, *PWWAN_VOICE_CLASS, wwan/WWAN_VOICE_CLASS, WwanVoiceClassNoVoice, wwan/WwanVoiceClassSimultaneousVoiceData, WWAN_VOICE_CLASS enumeration [Network Drivers Starting with Windows Vista], wwan/WwanVoiceClassSeparateVoiceData, wwan/WwanVoiceClassMax, WwanRef_13e9339b-e11b-416b-8335-51c950049c6e.xml, wwan/WwanVoiceClassNoVoice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
apiname:
-	WWAN_VOICE_CLASS
product: Windows
targetos: Windows
req.typenames: "*PWWAN_VOICE_CLASS, WWAN_VOICE_CLASS"
req.product: Windows 10 or later.
---

# _WWAN_VOICE_CLASS Enumeration
The WWAN_VOICE_CLASS enumeration lists the different types of voice classes that are supported by the
  MB device.

## Syntax
````
typedef enum _WWAN_VOICE_CLASS { 
  WwanVoiceClassUnknown                = 0,
  WwanVoiceClassNoVoice,
  WwanVoiceClassSeparateVoiceData,
  WwanVoiceClassSimultaneousVoiceData,
  WwanVoiceClassMax
} WWAN_VOICE_CLASS, *PWWAN_VOICE_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>WwanVoiceClassMax</td>
                    <td>The total number of supported cellular voice classes.</td>
                </tr>
            
                <tr>
                    <td>WwanVoiceClassNoVoice</td>
                    <td>The device does not support voice connections.</td>
                </tr>
            
                <tr>
                    <td>WwanVoiceClassSeparateVoiceData</td>
                    <td>The device supports separate voice and data connections.</td>
                </tr>
            
                <tr>
                    <td>WwanVoiceClassSimultaneousVoiceData</td>
                    <td>The device supports simultaneous voice and data connections.</td>
                </tr>
            
                <tr>
                    <td>WwanVoiceClassUnknown</td>
                    <td>The device uses an unknown method to support voice connections.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_VOICE_CLASS enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>