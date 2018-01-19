---
UID : NS:bthddi._BRB_GET_LOCAL_BD_ADDR
title : _BRB_GET_LOCAL_BD_ADDR
author : windows-driver-content
description : The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio.
old-location : bltooth\_brb_get_local_bd_addr.htm
old-project : bltooth
ms.assetid : cddaa92c-c43b-4875-a52e-a28ecc30962d
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BRB_GET_LOCAL_BD_ADDR,
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
req.alt-api : _BRB_GET_LOCAL_BD_ADDR
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
req.typenames : 
---

# _BRB_GET_LOCAL_BD_ADDR structure
The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio.

## Syntax
````
struct _BRB_GET_LOCAL_BD_ADDR {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
};
````

## Members

        
            `BtAddress`

            An output member that receives the address of the local radio.
        
            `Hdr`

            A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.

    ## Remarks
        To get the address of the local radio, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536611">
    BRB_HCI_GET_LOCAL_BD_ADDR</a> request.

Only a single local radio is supported by the Bluetooth driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536611">BRB_HCI_GET_LOCAL_BD_ADDR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_GET_LOCAL_BD_ADDR structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>