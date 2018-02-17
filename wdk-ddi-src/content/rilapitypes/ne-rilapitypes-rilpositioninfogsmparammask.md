---
UID: NE:rilapitypes.RILPOSITIONINFOGSMPARAMMASK
title: RILPOSITIONINFOGSMPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILPOSITIONINFOGSMPARAMMASK.
old-location: netvista\rilpositioninfogsmparammask.htm
old-project: netvista
ms.assetid: 9785ef86-8a2f-4e08-8caf-aa25f52a76ab
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilpositioninfogsmparammask, RIL_PARAM_POSITION_GSM_MCC, RIL_PARAM_POSITION_GSM_BSID, rilapitypes/RIL_PARAM_POSITION_GSM_MCC, RIL_PARAM_POSITION_GSM_ALL, rilapitypes/RIL_PARAM_POSITION_GSM_MNC, RIL_PARAM_POSITION_GSM_TA, RIL_PARAM_POSITION_GSM_ARFCN, RIL_PARAM_POSITION_GSM_LAC, RIL_PARAM_POSITION_GSM_MNC, rilapitypes/RIL_PARAM_POSITION_GSM_LAC, RIL_PARAM_POSITION_GSM_CELLID, rilapitypes/RIL_PARAM_POSITION_GSM_RXLEVEL, RILPOSITIONINFOGSMPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_GSM_RXLEVEL, rilapitypes/RIL_PARAM_POSITION_GSM_ALL, rilapitypes/RIL_PARAM_POSITION_GSM_CELLID, rilapitypes/RIL_PARAM_POSITION_GSM_ARFCN, RILPOSITIONINFOGSMPARAMMASK, rilapitypes/RIL_PARAM_POSITION_GSM_TA, rilapitypes/RILPOSITIONINFOGSMPARAMMASK, rilapitypes/RIL_PARAM_POSITION_GSM_BSID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPOSITIONINFOGSMPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFOGSMPARAMMASK
req.product: Windows 10 or later.
---

# RILPOSITIONINFOGSMPARAMMASK Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILPOSITIONINFOGSMPARAMMASK.

## Syntax
````
enum RILPOSITIONINFOGSMPARAMMASK {
  RIL_PARAM_POSITION_GSM_MCC      = 0x00000001, 
  RIL_PARAM_POSITION_GSM_MNC      = 0x00000002, 
  RIL_PARAM_POSITION_GSM_LAC      = 0x00000004, 
  RIL_PARAM_POSITION_GSM_CELLID   = 0x00000008, 
  RIL_PARAM_POSITION_GSM_TA       = 0x00000010, 
  RIL_PARAM_POSITION_GSM_ARFCN    = 0x00000020, 
  RIL_PARAM_POSITION_GSM_BSID     = 0x00000040, 
  RIL_PARAM_POSITION_GSM_RXLEVEL  = 0x00000080, 
  RIL_PARAM_POSITION_GSM_ALL      = 0x000000ff 

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_ARFCN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_BSID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_CELLID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_LAC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_MCC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_MNC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_RXLEVEL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_POSITION_GSM_TA</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOGSMPARAMMASK enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>