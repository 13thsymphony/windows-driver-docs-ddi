---
UID: NE:ntddrilapitypes.RILREGSTAT
title: RILREGSTAT
author: windows-driver-content
description: This enumeration describes the RILREGSTAT.
old-location: netvista\rilregstat.htm
old-project: netvista
ms.assetid: 53c72dbb-cf8d-4683-a440-985669265a52
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILREGSTAT, RILREGSTAT enumeration [Network Drivers Starting with Windows Vista], RIL_REGSTAT_ATTEMPTING, RIL_REGSTAT_DENIED, RIL_REGSTAT_HOME, RIL_REGSTAT_ROAMING, RIL_REGSTAT_ROAMING_INTL, RIL_REGSTAT_UNKNOWN, RIL_REGSTAT_UNREGISTERED, netvista.rilregstat, rilapitypes/RILREGSTAT, rilapitypes/RIL_REGSTAT_ATTEMPTING, rilapitypes/RIL_REGSTAT_DENIED, rilapitypes/RIL_REGSTAT_HOME, rilapitypes/RIL_REGSTAT_ROAMING, rilapitypes/RIL_REGSTAT_ROAMING_INTL, rilapitypes/RIL_REGSTAT_UNKNOWN, rilapitypes/RIL_REGSTAT_UNREGISTERED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
-	rilapitypes.h
api_name:
-	RILREGSTAT
product:
- Windows
targetos: Windows
req.typenames: RILREGSTAT
---

# RILREGSTAT Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILREGSTAT.

## Syntax
````
enum RILREGSTAT  {
  RIL_REGSTAT_UNKNOWN       = 0x00000000, 
  RIL_REGSTAT_UNREGISTERED  = 0x00000001, 
  RIL_REGSTAT_HOME          = 0x00000002, 
  RIL_REGSTAT_ATTEMPTING    = 0x00000003, 
  RIL_REGSTAT_DENIED        = 0x00000004, 
  RIL_REGSTAT_ROAMING       = 0x00000005, 
  RIL_REGSTAT_ROAMING_INTL  = 0x00000006 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_REGSTAT_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_UNREGISTERED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_HOME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_ATTEMPTING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_DENIED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_ROAMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_ROAMING_DOMESTIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_REGSTAT_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>