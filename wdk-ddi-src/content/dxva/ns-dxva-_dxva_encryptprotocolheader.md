---
UID: NS.DXVA._DXVA_ENCRYPTPROTOCOLHEADER
title: _DXVA_EncryptProtocolHeader
author: windows-driver-content
description: The DXVA_EncryptProtocolHeader structure is sent by the host decoder to the accelerator to indicate use of an encryption protocol.
old-location: display\dxva_encryptprotocolheader.htm
old-project: display
ms.assetid: 924da940-f609-4302-b454-87243200808e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_EncryptProtocolHeader, *LPDXVA_EncryptProtocolHeader, DXVA_EncryptProtocolHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_EncryptProtocolHeader
req.alt-loc: dxva.h
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

# _DXVA_EncryptProtocolHeader structure



## -description
The DXVA_EncryptProtocolHeader structure is sent by the host decoder to the accelerator to indicate use of an encryption protocol.



## -syntax

````
typedef struct _DXVA_EncryptProtocolHeader {
  DXVA_EncryptProtocolFunc dwFunction;
  DWORD                    ReservedBits[3];
  GUID                     guidEncryptProtocol;
} DXVA_EncryptProtocolHeader, *LPDXVA_EncryptProtocolHeader;
````


## -struct-fields

### -field dwFunction

Indicates whether encryption is being used and the operation to which encryption applies. The 24 most significant bits of <b>dwFunction</b> indicate that an encryption protocol is being used. These bits must be 0xFFFF00 when sent by the host software decoder, and 0xFFFF08 when sent by the accelerator. The 8 least significant bits of <b>dwFunction</b> contain a <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func</a> variable that indicates the operation to which the encryption protocol applies. Currently, the only relevant defined value of <i>bDXVA_Func</i> for use in these bits is 1, which indicates that the encryption protocol applies to compressed picture decoding.

There are only two possible values for <b>dwFunction</b> in this structure: 0xFFFF0001 when sent by a host software decoder, and 0xFFFF0801 when sent by the hardware accelerator.


### -field ReservedBits

Reserved bits used for packing and alignment. This must be zero.


### -field guidEncryptProtocol

Contains the GUID associated with the encryption protocol.


## -remarks
The encryption protocol in use is externally defined and operates as described in <a href="https://msdn.microsoft.com/d5ce9c02-7126-4775-bb87-dae45b93b652">Encryption Support</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>