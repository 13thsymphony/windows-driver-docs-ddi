---
UID: NE:ntddrilapitypes.RILOPERATORNAMESPARAMMASK
title: RILOPERATORNAMESPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILOPERATORNAMESPARAMMASK.
old-location: netvista\riloperatornamesparammask.htm
old-project: netvista
ms.assetid: f3e3654f-d317-4a8c-aa18-bbac86b06286
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILOPERATORNAMESPARAMMASK, RILOPERATORNAMESPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_ON_ALL, RIL_PARAM_ON_COUNTRY_CODE, RIL_PARAM_ON_LONGNAME, RIL_PARAM_ON_NUMNAME, RIL_PARAM_ON_SHORTNAME, RIL_PARAM_ON_SYSTEMTYPE, netvista.riloperatornamesparammask, rilapitypes/RILOPERATORNAMESPARAMMASK, rilapitypes/RIL_PARAM_ON_ALL, rilapitypes/RIL_PARAM_ON_COUNTRY_CODE, rilapitypes/RIL_PARAM_ON_LONGNAME, rilapitypes/RIL_PARAM_ON_NUMNAME, rilapitypes/RIL_PARAM_ON_SHORTNAME, rilapitypes/RIL_PARAM_ON_SYSTEMTYPE
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
-	RILOPERATORNAMESPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILOPERATORNAMESPARAMMASK
---

# RILOPERATORNAMESPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILOPERATORNAMESPARAMMASK.

## Syntax
````
enum RILOPERATORNAMESPARAMMASK {
  RIL_PARAM_ON_LONGNAME      = 0x00000001, 
  RIL_PARAM_ON_SHORTNAME     = 0x00000002, 
  RIL_PARAM_ON_NUMNAME       = 0x00000004, 
  RIL_PARAM_ON_COUNTRY_CODE  = 0x00000008, 
  RIL_PARAM_ON_SYSTEMTYPE    = 0x00000010, 
  RIL_PARAM_ON_ALL           = 0x0000001F 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_ON_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ON_COUNTRY_CODE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ON_LONGNAME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ON_NUMNAME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ON_SHORTNAME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_ON_SYSTEMTYPE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILOPERATORNAMESPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>