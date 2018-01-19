---
UID : NE:rilapitypes.RILDEVICEINFORMATION
title : RILDEVICEINFORMATION
author : windows-driver-content
description : This enumeration describes the RILDEVICEINFORMATION.
old-location : netvista\rildeviceinformation.htm
old-project : netvista
ms.assetid : 1abba51c-1db9-4424-aa11-64d3fd116a79
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILDEVICEINFORMATION, RILDEVICEINFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILDEVICEINFORMATION
req.alt-loc : rilapitypes.h
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
req.typenames : RILDEVICEINFORMATION
req.product : Windows 10 or later.
---

# RILDEVICEINFORMATION Enumeration


## Syntax
````
enum RILDEVICEINFORMATION {
  RIL_DEVICEINFO_MANUFACTURER       = 0x01, 
  RIL_DEVICEINFO_MODEL              = 0x02, 
  RIL_DEVICEINFO_REVISION           = 0x03, 
  RIL_DEVICEINFO_SERIALNUMBER_GW    = 0x04, 
  RIL_DEVICEINFO_SERIALNUMBER_CDMA  = 0x05, 
  RIL_DEVICEINFO_ARG_SMALLEST       = RIL_DEVICEINFO_MANUFACTURER, 
  RIL_DEVICEINFO_ARG_LARGEST        = RIL_DEVICEINFO_SERIALNUMBER_CDMA 

};
````

## Constants

<table>

<tr>
<td>RIL_DEVICEINFO_ARG_LARGEST</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_ARG_SMALLEST</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_MANUFACTURER</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_MODEL</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_REVISION</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_SERIALNUMBER_CDMA</td>
<td></td>
</tr>

<tr>
<td>RIL_DEVICEINFO_SERIALNUMBER_GW</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILDEVICEINFORMATION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>