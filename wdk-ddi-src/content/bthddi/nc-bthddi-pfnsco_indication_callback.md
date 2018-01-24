---
UID : NC:bthddi.PFNSCO_INDICATION_CALLBACK
title : PFNSCO_INDICATION_CALLBACK
author : windows-driver-content
description : Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection.
old-location : bltooth\sco_callback_function.htm
old-project : bltooth
ms.assetid : abc9fc88-6852-4bfb-8271-7a73a508c397
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : IBidiSpl2, IBidiSpl2::UnbindDevice, UnbindDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SCOIndicationCallback
req.alt-loc : bthddi.h
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
req.typenames : MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# PFNSCO_INDICATION_CALLBACK callback function
Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any
  changes to the status of a currently open SCO connection.

## Syntax

```
PFNSCO_INDICATION_CALLBACK PfnscoIndicationCallback;

void PfnscoIndicationCallback(
  IN PVOID Context,
  IN SCO_INDICATION_CODE Indication,
  IN PSCO_INDICATION_PARAMETERS Parameters
)
{...}
```

## Parameters

`Context`

For incoming remote connection request indications, this is the context specified by the profile
     driver in the 
     <b>IndicationCallbackContext</b> member of the 
     <a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a> structure
     when the profile driver registered the callback function. For changes to existing SCO connections, this
     is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a> BRB.

`Indication`

A 
     <a href="..\bthddi\ne-bthddi-_sco_indication_code.md">SCO_INDICATION_CODE</a> value that indicates
     the type of SCO event.

`Parameters`

A 
     <a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">
     SCO_INDICATION_PARAMETERS</a> structure that contains parameter information based on the value passed
     to the 
     <i>Indication</i> parameter.


## Return Value

None

## Remarks

The 
    <b>BtAddress</b> member found in the SCO_INDICATION_PARAMETERS structure passed in the 
    <i>Parameters</i> parameter indicates the Bluetooth address of the remote device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |
| **Library** |  |
| **IRQL** | Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a>
</dt>
<dt>
<a href="..\bthddi\ne-bthddi-_sco_indication_code.md">SCO_INDICATION_CODE</a>
</dt>
<dt>
<a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">SCO_INDICATION_PARAMETERS</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PFNSCO_INDICATION_CALLBACK callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>