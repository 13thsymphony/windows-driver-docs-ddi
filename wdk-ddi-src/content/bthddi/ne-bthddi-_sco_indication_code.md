---
UID: NE:bthddi._SCO_INDICATION_CODE
title: "_SCO_INDICATION_CODE"
author: windows-driver-content
description: The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding state change. The Bluetooth driver stack passes a value from this enumeration in the Indication argument of a profile driver's SCO Callback Function.
old-location: bltooth\sco_indication_code.htm
old-project: bltooth
ms.assetid: 4223dd79-cac7-41bd-8c94-12baf8e8367a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSCO_INDICATION_CODE, PSCO_INDICATION_CODE, PSCO_INDICATION_CODE enumeration pointer [Bluetooth Devices], SCO_INDICATION_CODE, SCO_INDICATION_CODE enumeration [Bluetooth Devices], ScoIndicationAddReference, ScoIndicationReleaseReference, ScoIndicationRemoteConnect, ScoIndicationRemoteDisconnect, _SCO_INDICATION_CODE, bltooth.sco_indication_code, bth_enums_e7290768-826f-4240-904c-07222b05d377.xml, bthddi/PSCO_INDICATION_CODE, bthddi/SCO_INDICATION_CODE, bthddi/ScoIndicationAddReference, bthddi/ScoIndicationReleaseReference, bthddi/ScoIndicationRemoteConnect, bthddi/ScoIndicationRemoteDisconnect"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	SCO_INDICATION_CODE
product:
- Windows
targetos: Windows
req.typenames: SCO_INDICATION_CODE, *PSCO_INDICATION_CODE
---

# _SCO_INDICATION_CODE Enumeration
The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding
  state change. The Bluetooth driver stack passes a value from this enumeration in the 
  <i>Indication</i> argument of a profile driver's 
  <a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>.

## Syntax
```
typedef enum _SCO_INDICATION_CODE {
  ScoIndicationAddReference      ,
  ScoIndicationReleaseReference  ,
  ScoIndicationRemoteConnect     ,
  ScoIndicationRemoteDisconnect
} SCO_INDICATION_CODE, *PSCO_INDICATION_CODE;
```

## Constants

<table>
            
                <tr>
                    <td>ScoIndicationAddReference</td>
                    <td>This value indicates that the profile driver should add one reference to its device object.</td>
                </tr>
            
                <tr>
                    <td>ScoIndicationReleaseReference</td>
                    <td>This value indicates that the profile driver can release one reference to its device
     object.</td>
                </tr>
            
                <tr>
                    <td>ScoIndicationRemoteConnect</td>
                    <td>This value indicates to a profile driver that a remote device is trying to connect to the local
     radio. Profile drivers accept or reject this request by 
     <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">building and sending</a> a 
     <a href="https://social.msdn.microsoft.com/Forums/en-US/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">
     BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request.</td>
                </tr>
            
                <tr>
                    <td>ScoIndicationRemoteDisconnect</td>
                    <td>This value indicates to a profile driver that a remote device is disconnecting from the local
     radio.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536751">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>