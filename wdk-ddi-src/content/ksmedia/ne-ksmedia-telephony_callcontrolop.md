---
UID: NE:ksmedia.TELEPHONY_CALLCONTROLOP
title: TELEPHONY_CALLCONTROLOP
author: windows-driver-content
description: The TELEPHONY_CALLCONTROLOP enumeration defines constants that specify an operation to perform on a phone call.
old-location: audio\telephony_callcontrolop.htm
old-project: audio
ms.assetid: 5E6ECBCB-53AC-440B-92D9-21F5A06FCFAB
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: TELEPHONY_CALLCONTROLOP, TELEPHONY_CALLCONTROLOP enumeration [Audio Devices], TELEPHONY_CALLCONTROLOP_DISABLE, TELEPHONY_CALLCONTROLOP_ENABLE, audio.telephony_callcontrolop, ksmedia/TELEPHONY_CALLCONTROLOP, ksmedia/TELEPHONY_CALLCONTROLOP_DISABLE, ksmedia/TELEPHONY_CALLCONTROLOP_ENABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10 Mobile
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
-	ksmedia.h
api_name:
-	TELEPHONY_CALLCONTROLOP
product:
- Windows
targetos: Windows
req.typenames: TELEPHONY_CALLCONTROLOP
---

# TELEPHONY_CALLCONTROLOP Enumeration
The <b>TELEPHONY_CALLCONTROLOP</b> enumeration defines constants that specify an operation to perform on a phone call.

## Syntax
```
typedef enum TELEPHONY_CALLCONTROLOP {
  TELEPHONY_CALLCONTROLOP_DISABLE  ,
  TELEPHONY_CALLCONTROLOP_ENABLE
} ;
```

## Constants

<table>
            
                <tr>
                    <td>TELEPHONY_CALLCONTROLOP_DISABLE</td>
                    <td>Disables a phone call.</td>
                </tr>
            
                <tr>
                    <td>TELEPHONY_CALLCONTROLOP_ENABLE</td>
                    <td>Enables a phone call.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Mobile Windows 10 Mobile |
| **Header** | ksmedia.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt169883">KSTELEPHONY_CALLCONTROL</a>