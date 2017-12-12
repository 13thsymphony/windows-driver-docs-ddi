---
UID: NE.ndis._IPSEC_OFFLOAD_V2_OPERATION
title: _IPSEC_OFFLOAD_V2_OPERATION
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security association (SA) is used.
old-location: netvista\ipsec_offload_v2_operation.htm
old-project: netvista
ms.assetid: bb26c8af-1564-4cf8-ab40-b50b4811466d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _IPSEC_OFFLOAD_V2_OPERATION, IPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPSEC_OFFLOAD_V2_OPERATION
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _IPSEC_OFFLOAD_V2_OPERATION enumeration



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security
  association (SA) is used.



## -syntax

````
typedef enum _IPSEC_OFFLOAD_V2_OPERATION { 
  IPsecOffloadV2Ah   = 1,
  IPsecOffloadV2Esp,
  IPsecOffloadV2Max
} IPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION;
````


## -enum-fields

### -field IPsecOffloadV2Ah

The SA is used for authentication (integrity checking).


### -field IPsecOffloadV2Esp

The SA is used for encryption/decryption (confidentiality).


### -field IPsecOffloadV2Max

Reserved for NDIS.


## -remarks
The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the operation for which an SA is used in the 
    <b>Operation</b> member of the 
    <a href="netvista.ipsec_offload_v2_security_association">
    IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.1 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ipsec_offload_v2_security_association">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_OPERATION enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

