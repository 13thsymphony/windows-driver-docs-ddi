---
UID: NE:wwan._WWAN_DEVICE_TYPE
title: "_WWAN_DEVICE_TYPE"
author: windows-driver-content
description: The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.
old-location: netvista\wwan_device_type.htm
old-project: netvista
ms.assetid: ad99b2b0-d62a-4e3e-a368-b9109f0fefb4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/WwanDeviceTypeRemote, wwan/PWWAN_DEVICE_TYPE, wwan/WWAN_DEVICE_TYPE, WwanDeviceTypeUnknown, WwanDeviceTypeRemovable, WWAN_DEVICE_TYPE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanDeviceTypeEmbedded, PWWAN_DEVICE_TYPE, wwan/WwanDeviceTypeRemovable, _WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE, WwanDeviceTypeMax, netvista.wwan_device_type, PWWAN_DEVICE_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanDeviceTypeUnknown, WwanDeviceTypeEmbedded, WwanDeviceTypeRemote, wwan/WwanDeviceTypeMax, WwanRef_7a7adc94-ea69-4327-b9b6-467a1c784979.xml, WWAN_DEVICE_TYPE
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
-	WWAN_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_TYPE Enumeration
The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.

## Syntax
````
typedef enum _WWAN_DEVICE_TYPE { 
  WwanDeviceTypeUnknown    = 0,
  WwanDeviceTypeEmbedded,
  WwanDeviceTypeRemovable,
  WwanDeviceTypeRemote,
  WwanDeviceTypeMax
} WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanDeviceTypeEmbedded</td>
                    <td>The device type is embedded in the system.</td>
                </tr>
            
                <tr>
                    <td>WwanDeviceTypeMax</td>
                    <td>The total number of supported device types.</td>
                </tr>
            
                <tr>
                    <td>WwanDeviceTypeRemote</td>
                    <td>The device type is remote. For example, a tethered cellular phone modem.</td>
                </tr>
            
                <tr>
                    <td>WwanDeviceTypeRemovable</td>
                    <td>The device type is removable.</td>
                </tr>
            
                <tr>
                    <td>WwanDeviceTypeUnknown</td>
                    <td>The device type is unknown.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>