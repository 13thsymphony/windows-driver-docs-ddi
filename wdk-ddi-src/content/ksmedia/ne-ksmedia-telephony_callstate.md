---
UID: NE:ksmedia.TELEPHONY_CALLSTATE
title: TELEPHONY_CALLSTATE
author: windows-driver-content
description: The TELEPHONY_CALLSTATE enumeration defines constants that specify the state of a phone call.
old-location: audio\telephony_callstate.htm
old-project: audio
ms.assetid: 8191418A-7139-4BF4-9869-F21AA54EA8B3
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: TELEPHONY_CALLSTATE, TELEPHONY_CALLSTATE enumeration [Audio Devices], TELEPHONY_CALLSTATE_DISABLED, TELEPHONY_CALLSTATE_ENABLED, TELEPHONY_CALLSTATE_HOLD, TELEPHONY_CALLSTATE_PROVIDERTRANSITION, audio.telephony_callstate, ksmedia/TELEPHONY_CALLSTATE, ksmedia/TELEPHONY_CALLSTATE_DISABLED, ksmedia/TELEPHONY_CALLSTATE_ENABLED, ksmedia/TELEPHONY_CALLSTATE_HOLD, ksmedia/TELEPHONY_CALLSTATE_PROVIDERTRANSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: None supported
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
-	TELEPHONY_CALLSTATE
product:
- Windows
targetos: Windows
req.typenames: TELEPHONY_CALLSTATE
---

# TELEPHONY_CALLSTATE Enumeration
The <b>TELEPHONY_CALLSTATE</b> enumeration defines constants that specify the state of a phone call.

## Syntax
```
typedef enum TELEPHONY_CALLSTATE {
  TELEPHONY_CALLSTATE_DISABLED            ,
  TELEPHONY_CALLSTATE_ENABLED             ,
  TELEPHONY_CALLSTATE_HOLD                ,
  TELEPHONY_CALLSTATE_PROVIDERTRANSITION
} ;
```

## Constants

<table>
            
                <tr>
                    <td>TELEPHONY_CALLSTATE_DISABLED</td>
                    <td>Specifies that the phone call is disabled.</td>
                </tr>
            
                <tr>
                    <td>TELEPHONY_CALLSTATE_ENABLED</td>
                    <td>Specifies that the phone call is enabled. This constant is set in a number of situations. For example, it will be set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_END</b> and when <b>TELEPHONY_CALLCONTROLOP_ENABLE</b> is received.</td>
                </tr>
            
                <tr>
                    <td>TELEPHONY_CALLSTATE_HOLD</td>
                    <td>Specifies that the phone call is on hold.</td>
                </tr>
            
                <tr>
                    <td>TELEPHONY_CALLSTATE_PROVIDERTRANSITION</td>
                    <td>Specifies that the phone call is disabled. This constant is set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_BEGIN</b>.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10,Windows 10 Mobile Windows 10,Windows 10 Mobile |
| **Header** | ksmedia.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt169884">KSTELEPHONY_CALLINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt169898">TELEPHONY_PROVIDERCHANGEOP</a>