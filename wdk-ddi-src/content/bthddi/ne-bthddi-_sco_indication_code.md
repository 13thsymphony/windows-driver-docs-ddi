---
UID : NE:bthddi._SCO_INDICATION_CODE
title : _SCO_INDICATION_CODE
author : windows-driver-content
description : The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding state change. The Bluetooth driver stack passes a value from this enumeration in the Indication argument of a profile driver's SCO Callback Function.
old-location : bltooth\sco_indication_code.htm
old-project : bltooth
ms.assetid : 4223dd79-cac7-41bd-8c94-12baf8e8367a
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bthddi/ScoIndicationRemoteDisconnect, bthddi/ScoIndicationAddReference, bth_enums_e7290768-826f-4240-904c-07222b05d377.xml, SCO_INDICATION_CODE enumeration [Bluetooth Devices], bthddi/ScoIndicationRemoteConnect, bthddi/PSCO_INDICATION_CODE, bthddi/SCO_INDICATION_CODE, ScoIndicationAddReference, PSCO_INDICATION_CODE, *PSCO_INDICATION_CODE, _SCO_INDICATION_CODE, SCO_INDICATION_CODE, ScoIndicationRemoteDisconnect, ScoIndicationReleaseReference, ScoIndicationRemoteConnect, bthddi/ScoIndicationReleaseReference, bltooth.sco_indication_code, PSCO_INDICATION_CODE enumeration pointer [Bluetooth Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SCO_INDICATION_CODE, *PSCO_INDICATION_CODE
---

# _SCO_INDICATION_CODE Enumeration
The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding
  state change. The Bluetooth driver stack passes a value from this enumeration in the 
  <i>Indication</i> argument of a profile driver's 
  <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>.

## Syntax
````
typedef enum _SCO_INDICATION_CODE { 
  ScoIndicationAddReference      = 0,
  ScoIndicationReleaseReference  = 1,
  ScoIndicationRemoteConnect     = 2,
  ScoIndicationRemoteDisconnect  = 3
} SCO_INDICATION_CODE, *PSCO_INDICATION_CODE;
````

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
     <mshelp:link keywords="bltooth.brb_sco_open_channel_response" tabindex="0"><b>
     BRB_SCO_OPEN_CHANNEL_RESPONSE</b></mshelp:link> request.</td>
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a>

<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>

<a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SCO_INDICATION_CODE enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>