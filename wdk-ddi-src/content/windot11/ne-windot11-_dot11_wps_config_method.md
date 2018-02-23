---
UID: NE:windot11._DOT11_WPS_CONFIG_METHOD
title: "_DOT11_WPS_CONFIG_METHOD"
author: windows-driver-content
description: The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.
old-location: netvista\dot11_wps_config_method.htm
old-project: netvista
ms.assetid: FFA5B3FF-57AF-4701-97FB-E1182CDE8F7A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: windot11/DOT11_WPS_CONFIG_METHOD_DISPLAY, windot11/DOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD_DISPLAY, DOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD enumeration [Network Drivers Starting with Windows Vista], windot11/DOT11_WPS_CONFIG_METHOD_PUSHBUTTON, DOT11_WPS_CONFIG_METHOD_PUSHBUTTON, *PDOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD_NULL, DOT11_WPS_CONFIG_METHOD_KEYPAD, windot11/DOT11_WPS_CONFIG_METHOD_NULL, windot11/DOT11_WPS_CONFIG_METHOD_KEYPAD, _DOT11_WPS_CONFIG_METHOD, netvista.dot11_wps_config_method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	Windot11.h
apiname:
-	DOT11_WPS_CONFIG_METHOD
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_CONFIG_METHOD, *PDOT11_WPS_CONFIG_METHOD
req.product: Windows 10 or later.
---

# _DOT11_WPS_CONFIG_METHOD Enumeration
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.

## Syntax
````
typedef enum _DOT11_WPS_CONFIG_METHOD { 
  DOT11_WPS_CONFIG_METHOD_NULL        = 0,
  DOT11_WPS_CONFIG_METHOD_DISPLAY     = 0x0008,
  DOT11_WPS_CONFIG_METHOD_PUSHBUTTON  = 0x0080,
  DOT11_WPS_CONFIG_METHOD_KEYPAD      = 0x0100
} DOT11_WPS_CONFIG_METHOD;
````

## Constants

<table>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_DISPLAY</td>
                    <td>Setup is configured by a software user interface.</td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_KEYPAD</td>
                    <td>Setup is configured by a keypad action.</td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_NFC_INTERFACE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_NFC_TAG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_NULL</td>
                    <td>No setup method is configured.</td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_PUSHBUTTON</td>
                    <td>Setup is configured by push button enablement.</td>
                </tr>
            
                <tr>
                    <td>DOT11_WPS_CONFIG_METHOD_WFDS_DEFAULT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | windot11.h |