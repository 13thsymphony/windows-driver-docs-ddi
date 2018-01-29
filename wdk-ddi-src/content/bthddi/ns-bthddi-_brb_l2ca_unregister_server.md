---
UID : NS:bthddi._BRB_L2CA_UNREGISTER_SERVER
title : _BRB_L2CA_UNREGISTER_SERVER
author : windows-driver-content
description : A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices.
old-location : bltooth\_brb_l2ca_unregister_server.htm
old-project : bltooth
ms.assetid : bc10d76f-da09-457a-b469-ef59d1cb09d9
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bthddi/_BRB_L2CA_UNREGISTER_SERVER, _BRB_L2CA_UNREGISTER_SERVER structure [Bluetooth Devices], _BRB_L2CA_UNREGISTER_SERVER, bth_structs_211f7f5f-0a2d-487e-9720-78076b36e012.xml, bltooth._brb_l2ca_unregister_server
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
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
req.typenames : 
---

# _BRB_L2CA_UNREGISTER_SERVER structure
A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving L2CAP connections from remote Bluetooth devices.

## Syntax
````
struct _BRB_L2CA_UNREGISTER_SERVER {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
  PVOID      ServerHandle;
  USHORT     Psm;
};
````

## Members


`BtAddress`

The address of the remote device.

`Hdr`

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.

`Psm`

The Protocol/Service Multiplexer (PSM) that was specified in a previous 
     <mshelp:link keywords="bltooth.brb_l2ca_register_server" tabindex="0"><b>
     BRB_L2CA_REGISTER_SERVER</b></mshelp:link> request.

`ServerHandle`

The handle of the L2CAP server to unregister, as returned earlier from a previous 
     <mshelp:link keywords="bltooth.brb_l2ca_register_server" tabindex="0"><b>
     BRB_L2CA_REGISTER_SERVER</b></mshelp:link> request.

## Remarks
To unregister itself as a L2CAP server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <mshelp:link keywords="bltooth.brb_l2ca_unregister_server" tabindex="0"><b>
    BRB_L2CA_UNREGISTER_SERVER</b></mshelp:link> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536862">BRB_L2CA_UNREGISTER_SERVER</a>

<a href="..\bthddi\ns-bthddi-_brb_l2ca_register_server.md">_BRB_L2CA_REGISTER_SERVER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_UNREGISTER_SERVER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>