---
UID: NE:wwan._WWAN_EMERGENCY_MODE
title: "_WWAN_EMERGENCY_MODE"
author: windows-driver-content
description: The WWAN_EMERGENCY_MODE enumeration lists the different types of emergency modes that are supported by the MB device.
old-location: netvista\wwan_emergency_mode.htm
old-project: netvista
ms.assetid: d901e763-5e1c-443d-ba9c-9d1e4413bd47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/WWAN_EMERGENCY_MODE, WwanEmergencyModeOff, _WWAN_EMERGENCY_MODE, netvista.wwan_emergency_mode, WwanEmergencyModeOn, WwanRef_8b2029ff-7d10-4f36-a4c0-6b41f464b726.xml, *PWWAN_EMERGENCY_MODE, wwan/WwanEmergencyModeOff, WWAN_EMERGENCY_MODE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanEmergencyModeMax, wwan/PWWAN_EMERGENCY_MODE, wwan/WwanEmergencyModeOn, WWAN_EMERGENCY_MODE, WwanEmergencyModeMax, PWWAN_EMERGENCY_MODE enumeration pointer [Network Drivers Starting with Windows Vista], PWWAN_EMERGENCY_MODE
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
-	WWAN_EMERGENCY_MODE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_EMERGENCY_MODE, WWAN_EMERGENCY_MODE"
req.product: Windows 10 or later.
---

# _WWAN_EMERGENCY_MODE Enumeration
The WWAN_EMERGENCY_MODE enumeration lists the different types of emergency modes that are supported
  by the MB device.

## Syntax
````
typedef enum _WWAN_EMERGENCY_MODE { 
  WwanEmergencyModeOff  = 0,
  WwanEmergencyModeOn,
  WwanEmergencyModeMax
} WWAN_EMERGENCY_MODE, *PWWAN_EMERGENCY_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanEmergencyModeMax</td>
                    <td>The total number of supported emergency modes.</td>
                </tr>
            
                <tr>
                    <td>WwanEmergencyModeOff</td>
                    <td>The device is in normal mode.</td>
                </tr>
            
                <tr>
                    <td>WwanEmergencyModeOn</td>
                    <td>The device is in emergency mode. An example of an emergency mode function is a call to 911.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

    ## See Also

        <a href="..\wwan\ns-wwan-_wwan_ready_info.md">WWAN_READY_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_EMERGENCY_MODE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>