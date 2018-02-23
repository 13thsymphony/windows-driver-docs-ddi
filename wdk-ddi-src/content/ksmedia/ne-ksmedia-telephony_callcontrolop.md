---
UID: NE:ksmedia.TELEPHONY_CALLCONTROLOP
title: TELEPHONY_CALLCONTROLOP
author: windows-driver-content
description: The TELEPHONY_CALLCONTROLOP enumeration defines constants that specify an operation to perform on a phone call.
old-location: audio\telephony_callcontrolop.htm
old-project: audio
ms.assetid: 5E6ECBCB-53AC-440B-92D9-21F5A06FCFAB
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: TELEPHONY_CALLCONTROLOP_ENABLE, ksmedia/TELEPHONY_CALLCONTROLOP, ksmedia/TELEPHONY_CALLCONTROLOP_ENABLE, TELEPHONY_CALLCONTROLOP, audio.telephony_callcontrolop, TELEPHONY_CALLCONTROLOP enumeration [Audio Devices], TELEPHONY_CALLCONTROLOP_DISABLE, ksmedia/TELEPHONY_CALLCONTROLOP_DISABLE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	TELEPHONY_CALLCONTROLOP
product: Windows
targetos: Windows
req.typenames: TELEPHONY_CALLCONTROLOP
---

# TELEPHONY_CALLCONTROLOP Enumeration
The <b>TELEPHONY_CALLCONTROLOP</b> enumeration defines constants that specify an operation to perform on a phone call.

## Syntax
````
typedef enum  { 
  TELEPHONY_CALLCONTROLOP_DISABLE  = 0,
  TELEPHONY_CALLCONTROLOP_ENABLE   = 1
} TELEPHONY_CALLCONTROLOP;
````

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

<a href="..\ksmedia\ns-ksmedia-_tagkstelephony_callcontrol.md">KSTELEPHONY_CALLCONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20TELEPHONY_CALLCONTROLOP enumeration%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>