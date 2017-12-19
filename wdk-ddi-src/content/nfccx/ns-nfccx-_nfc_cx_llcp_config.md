---
UID: NS.NFCCX._NFC_CX_LLCP_CONFIG
title: _NFC_CX_LLCP_CONFIG
author: windows-driver-content
description: The NFC_CX_LLCP_CONFIG structure is an input parameter to NfcCxSetLlcpConfig.
old-location: nfpdrivers\nfc_cx_llcp_config.htm
old-project: nfpdrivers
ms.assetid: 84A1F957-FAAE-4C2D-9D49-486813A26950
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG, PNFC_CX_LLCP_CONFIG, *PNFC_CX_LLCP_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFC_CX_LLCP_CONFIG
req.alt-loc: nfccx.h
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
---

# _NFC_CX_LLCP_CONFIG structure



## -description
The NFC_CX_LLCP_CONFIG structure is an input parameter to <a href="nfpdrivers._nfccxsetllcpconfig">NfcCxSetLlcpConfig.</a>




## -syntax

````
typedef struct _NFC_CX_LLCP_CONFIG {
  ULONG  Size;
  USHORT Miu;
  UCHAR  LinkTimeout;
  UCHAR  RecvWindowSize;
} NFC_CX_LLCP_CONFIG, *PNFC_CX_LLCP_CONFIG;
````


## -struct-fields

### -field Size

 Size of this structure in bytes.


### -field Miu

Max information unit in bytes. Default is 1024.


### -field LinkTimeout

 LTO timeout in multiples of 10 milliseconds. Default is 100 (1 second).


### -field RecvWindowSize

The receive window size per LLCP spec. Default value is 5.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfccx.h (include Ncidef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_LLCP_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

