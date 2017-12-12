---
UID: NS.WINSMCRD._SCARD_IO_REQUEST
title: _SCARD_IO_REQUEST
author: windows-driver-content
description: This structure is used to identify a smart card I/O request.
old-location: nfpdrivers\scard_io_request_structure.htm
old-project: nfpdrivers
ms.assetid: DE670712-2F11-4BB0-ADC7-B68C94EF0759
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SCARD_IO_REQUEST, SCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, *PSCARD_IO_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsmcrd.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCARD_IO_REQUEST
req.alt-loc: winsmcrd.h
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
req.product: Windows 10 or later.
---

# _SCARD_IO_REQUEST structure



## -description
This structure is used to identify a smart card I/O request.



## -syntax

````
typedef struct _SCARD_IO_REQUEST {
  DWORD  dwProtocol;
  DWORD  cbPciLength;
} SCARD_IO_REQUEST, *PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST;
````


## -struct-fields

### -field dwProtocol

Specifies the protocol ID.


### -field cbPciLength

Specifies the protocol control information length.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsmcrd.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20SCARD_IO_REQUEST  structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

