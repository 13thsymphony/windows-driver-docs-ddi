---
UID: NE:windot11._DOT11_TEMP_TYPE
title: "_DOT11_TEMP_TYPE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_temp_type.htm
old-project: netvista
ms.assetid: 73275e2e-b738-4adc-b89e-2cd152de6c75
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_TEMP_TYPE, DOT11_TEMP_TYPE, DOT11_TEMP_TYPE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5b580f41-75a6-4d16-9ea5-cc3dc3622a84.xml, PDOT11_TEMP_TYPE, PDOT11_TEMP_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_TEMP_TYPE, dot11_temp_type_1, dot11_temp_type_2, dot11_temp_type_unknown, netvista.dot11_temp_type, windot11/DOT11_TEMP_TYPE, windot11/PDOT11_TEMP_TYPE, windot11/dot11_temp_type_1, windot11/dot11_temp_type_2, windot11/dot11_temp_type_unknown"
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
-	DOT11_TEMP_TYPE
product: Windows
targetos: Windows
req.typenames: DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE
req.product: Windows 10 or later.
---

# _DOT11_TEMP_TYPE Enumeration
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_TEMP_TYPE enumeration specifies the operating temperature range of a PHY on the 802.11
  station.

## Syntax
````
typedef enum _DOT11_TEMP_TYPE { 
  dot11_temp_type_unknown  = 0,
  dot11_temp_type_1        = 1,
  dot11_temp_type_2        = 2
} DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>dot11_temp_type_unknown</td>
                    <td>An uninitialized or unknown temperature type.</td>
                </tr>
            
                <tr>
                    <td>dot11_temp_type_1</td>
                    <td>The commercial temperature range from 0 through 40 degrees Celsius.</td>
                </tr>
            
                <tr>
                    <td>dot11_temp_type_2</td>
                    <td>The industrial temperature range from -30 through 70 degrees Celsius.</td>
                </tr>
</table>

## Remarks

There are different operating temperature requirements dependent on the anticipated environmental
    conditions. The DOT11_TEMP_TYPE enumeration describes a PHY's operating temperature range capability.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569431">OID_DOT11_TEMP_TYPE</a>