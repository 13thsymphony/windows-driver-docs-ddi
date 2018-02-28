---
UID: NE:windot11.DOT11_DIRECTION
title: DOT11_DIRECTION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_direction.htm
old-project: netvista
ms.assetid: 83a83af9-314a-49c1-b241-a0ef0716f83a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_DIRECTION, DOT11_DIRECTION, DOT11_DIRECTION enumeration [Network Drivers Starting with Windows Vista], DOT11_DIR_BOTH, DOT11_DIR_INBOUND, DOT11_DIR_OUTBOUND, Native_802.11_data_types_aef66faf-de2c-42f1-a213-ed12ea7ef583.xml, PDOT11_DIRECTION, PDOT11_DIRECTION enumeration pointer [Network Drivers Starting with Windows Vista], netvista.dot11_direction, windot11/DOT11_DIRECTION, windot11/DOT11_DIR_BOTH, windot11/DOT11_DIR_INBOUND, windot11/DOT11_DIR_OUTBOUND, windot11/PDOT11_DIRECTION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	windot11.h
api_name:
-	DOT11_DIRECTION
product: Windows
targetos: Windows
req.typenames: DOT11_DIRECTION, *PDOT11_DIRECTION
req.product: Windows 10 or later.
---

# DOT11_DIRECTION Enumeration
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DIRECTION enumeration specifies whether the 802.11 station uses a cipher key to decrypt
  received packets and/or encrypt transmitted packets.

## Syntax
````
typedef enum DOT11_DIRECTION { 
  DOT11_DIR_INBOUND   = 1,
  DOT11_DIR_OUTBOUND  = 2,
  DOT11_DIR_BOTH      = 3
} DOT11_DIRECTION, *PDOT11_DIRECTION;
````

## Constants

<table>
            
                <tr>
                    <td>DOT11_DIR_BOTH</td>
                    <td>The 802.11 station uses the cipher key for packets received from or transmitted to the AP or peer
     station.</td>
                </tr>
            
                <tr>
                    <td>DOT11_DIR_INBOUND</td>
                    <td>The 802.11 station uses the cipher key to decrypt packets received from the access point (AP) or
     peer station.</td>
                </tr>
            
                <tr>
                    <td>DOT11_DIR_OUTBOUND</td>
                    <td>The 802.11 station uses the cipher key to encrypt packets transmitted to the AP or peer
     station.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">Dot11ExtSetDefaultKey</a>



<a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_DIRECTION enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>