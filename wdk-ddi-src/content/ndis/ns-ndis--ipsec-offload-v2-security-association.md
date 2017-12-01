---
UID: NS.ndis._IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
title: IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\ipsec_offload_v2_security_association.htm
old-project: netvista
ms.assetid: b2c5611e-930d-41a5-a07e-7de8f8584283
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, *PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
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
req.irql: See Remarks section
req.iface: 
---

# IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]</p>
<p>The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure specifies a single security association
  (SA).</p>


## -syntax

````
typedef struct _IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION {
  ULONG                           Flags;
  IPSEC_OFFLOAD_V2_OPERATION      Operation;
  IPSEC_OFFLOAD_V2_SPI_TYPE       Spi;
  IPSEC_OFFLOAD_V2_ALGORITHM_INFO AuthenticationAlgorithm;
  IPSEC_OFFLOAD_V2_ALGORITHM_INFO EncryptionAlgorithm;
  ULONG                           SequenceNumberHighOrder;
} IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, *PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>A set of flags that can be combined with a bitwise OR operation. Otherwise, set this member to
     zero. The following values are valid:
     </p>
<p></p>
<dl>

### -field <a id="IPSEC_OFFLOAD_V2_ESN_SA"></a><a id="ipsec_offload_v2_esn_sa"></a>IPSEC_OFFLOAD_V2_ESN_SA

<dd>
<p>Specifies ESN SA.</p>
</dd>
</dl>
</dd>

### -field <b>Operation</b>

<dd>
<p>The IPsec operation for which the SA is to be used. The 
     <a href="..\ndis\ne-ndis--ipsec-offload-v2-operation.md">
     IPSEC_OFFLOAD_V2_OPERATION</a> enumeration defines the supported operations.</p>
</dd>

### -field <b>Spi</b>

<dd>
<p>A 32 bit security parameters index (SPI) for the SA.</p>
</dd>

### -field <b>AuthenticationAlgorithm</b>

<dd>
<p>The integrity (authentication) algorithm for the SA, formatted as an 
     <a href="..\ndis\ns-ndis--ipsec-offload-v2-algorithm-info.md">
     IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a> structure.</p>
</dd>

### -field <b>EncryptionAlgorithm</b>

<dd>
<p>The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure. 
     </p>
<div class="alert"><b>Note</b>  For AES-GCM, the 
     <b>EncryptionAlgorithm</b> member contains the key information. The 
     <b>AuthenticationAlgorithm</b> member of IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, and the key length and
     offset in IPSEC_OFFLOAD_V2_ALGORITHM_INFO, should not be used.</div>
<div> </div>
</dd>

### -field <b>SequenceNumberHighOrder</b>

<dd>
<p>The sequence number high-order extension. This sequence number high-order extension is defined in
     RFC 4304. This member represents the high-order portion of the sequence number that is not included in
     the IPsec header.</p>
</dd>
</dl>

## -remarks
<p>The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure is an element in the 
    <b>SecAssoc</b> variable-length array in the 
    <a href="..\ndis\ns-ndis--ipsec-offload-v2-add-sa.md">IPSEC_OFFLOAD_V2_ADD_SA</a> structure.
    The number of SAs in the IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure is specified in the 
    <b>NumExtHdrs</b> member of IPSEC_OFFLOAD_V2_ADD_SA.</p>

<p>A 
    <b>SecAssoc</b> element that is specified for use in processing authentication headers (AH) will have an
    operation type (the 
    <b>Operation</b> member) of 
    <b>IPsecOffloadV2Ah</b> and will have the authentication algorithm in the 
    <b>AuthenticationAlgorithm</b> member. The SA will not have an encryption algorithm in the 
    <b>EncryptionAlgorithm</b> member, so 
    <b>EncryptionAlgorithm</b> will contain zeros.</p>

<p>A 
    <b>SecAssoc</b> element that is specified for use in processing encapsulating security payloads (ESPs)
    will have an operation type (the 
    <b>Operation</b> member) of 
    <b>IPsecOffloadV2Esp</b> and can have an authentication algorithm, an encryption algorithm, or both. Note
    that for combined mode algorithms, only the 
    <b>EncryptionAlgorithm</b> member will be specified.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ndis\ns-ndis--ipsec-offload-v2-add-sa.md">IPSEC_OFFLOAD_V2_ADD_SA</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ipsec-offload-v2-algorithm-info.md">
   IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a>
</dt>
<dt>
<a href="..\ndis\ne-ndis--ipsec-offload-v2-operation.md">IPSEC_OFFLOAD_V2_OPERATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
