---
UID: NE:d3dkmddi._DXGK_WDDMVERSION
title: "_DXGK_WDDMVERSION"
author: windows-driver-content
description: The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.
old-location: display\dxgk_wddmversion.htm
old-project: display
ms.assetid: 2360224a-fa99-4b2c-a346-0129e3e95cd7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGKDDI_WDDMv2, DXGK_WDDMVERSION enumeration [Display Devices], d3dkmddi/DXGKDDI_WDDMv1, DmEnums_3a73843a-4967-4faa-a217-42487ae4f865.xml, _DXGK_WDDMVERSION, display.dxgk_wddmversion, DXGKDDI_WDDMv1, d3dkmddi/DXGK_WDDMVERSION, DXGKDDI_WDDMv1_2, d3dkmddi/DXGKDDI_WDDMv2, DXGK_WDDMVERSION, d3dkmddi/DXGKDDI_WDDMv1_2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_WDDMVERSION
product: Windows
targetos: Windows
req.typenames: DXGK_WDDMVERSION
---

# _DXGK_WDDMVERSION Enumeration
The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.

## Syntax
````
typedef enum _DXGK_WDDMVERSION { 
  DXGKDDI_WDDMv1    = 0x1000,
  DXGKDDI_WDDMv1_2  = 0x1200,
  DXGKDDI_WDDMv2    = 0x2000
} DXGK_WDDMVERSION;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKDDI_WDDMv1</td>
                    <td>Reserved for system use.


<div class="alert"><b>Note</b>  If a driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), set the <b>WDDMVersion</b> member of the  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure to DXGKDDI_WDDMv1.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv1_2</td>
                    <td>Supported beginning with Windows 8.

Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv1_3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv2</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv2_1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv2_2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKDDI_WDDMv2_3</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn Interface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_WDDMVERSION enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>