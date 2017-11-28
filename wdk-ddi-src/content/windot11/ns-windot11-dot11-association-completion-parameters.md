---
UID: NS.windot11.DOT11_ASSOCIATION_COMPLETION_PARAMETERS
title: DOT11_ASSOCIATION_COMPLETION_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_association_completion_parameters.htm
old-project: netvista
ms.assetid: 770962e3-0339-46f8-a789-7c9bbf9e058f
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: DOT11_ASSOCIATION_COMPLETION_PARAMETERS, DOT11_ASSOCIATION_COMPLETION_PARAMETERS, *PDOT11_ASSOCIATION_COMPLETION_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_ASSOCIATION_COMPLETION_PARAMETERS
req.alt-loc: windot11.h
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
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure



## -description

## -syntax

````
typedef struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  DOT11_MAC_ADDRESS      MacAddr;
  DOT11_ASSOC_STATUS     uStatus;
  BOOLEAN                bReAssocReq;
  BOOLEAN                bReAssocResp;
  ULONG                  uAssocReqOffset;
  ULONG                  uAssocReqSize;
  ULONG                  uAssocRespOffset;
  ULONG                  uAssocRespSize;
  ULONG                  uBeaconOffset;
  ULONG                  uBeaconSize;
  ULONG                  uIHVDataOffset;
  ULONG                  uIHVDataSize;
  DOT11_AUTH_ALGORITHM   AuthAlgo;
  DOT11_CIPHER_ALGORITHM UnicastCipher;
  DOT11_CIPHER_ALGORITHM MulticastCipher;
  ULONG                  uActivePhyListOffset;
  ULONG                  uActivePhyListSize;
  BOOLEAN                bFourAddressSupported;
  BOOLEAN                bPortAuthorized;
  UCHAR                  ucActiveQoSProtocol;
  DOT11_DS_INFO          DSInfo;
  ULONG                  uEncapTableOffset;
  ULONG                  uEncapTableSize;
  DOT11_CIPHER_ALGORITHM MulticastMgmtCipher;
  ULONG                  uAssocComebackTime;
} DOT11_ASSOCIATION_COMPLETION_PARAMETERS, *PDOT11_ASSOCIATION_COMPLETION_PARAMETERS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure. This member
     is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.
     </p>
<p>The miniport driver must set the members of 
     <i>Header</i> to the following values:</p>
<p></p>
<dl>

### -field <a id="Type"></a><a id="type"></a><a id="TYPE"></a><b>Type</b>

<dd>
<p>This member must be set to NDIS_OBJECT_TYPE_DEFAULT.</p>
</dd>

### -field <a id="Revision"></a><a id="revision"></a><a id="REVISION"></a><b>Revision</b>

<dd>
<p>This member must be set to DOT11_ASSOCIATION_COMPLETION_PARAMETERS_REVISION_1.</p>
</dd>

### -field <a id="Size"></a><a id="size"></a><a id="SIZE"></a><b>Size</b>

<dd>
<p>This member must be set to 
       <code>sizeof(DOT11_ASSOCIATION_COMPLETION_PARAMETERS)</code>.</p>
</dd>
</dl>
<p>For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field <b>MacAddr</b>

<dd>
<p>The media access control (MAC) address of the access point (AP) (for infrastructure BSS networks)
     or peer station (for independent BSS (IBSS) networks) that the 802.11 station attempted to connect
     to.</p>
</dd>

### -field <b>uStatus</b>

<dd>
<p>The completion status of the association operation, as specified by a value defined for 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>.</p>
</dd>

### -field <b>bReAssocReq</b>

<dd>
<p>A Boolean value that indicates whether the 802.11 station sent an 802.11 Association or
     Reassociation frame to the AP. If <b>TRUE</b>, the 802.11 station sent an 801.11 Reassociation Request frame to
     the AP. If <b>FALSE</b>, the 802.11 station sent an 802.11 Association Request frame to the AP. 
     </p>
<p>A value of <b>TRUE</b> for the 
     <b>bReAssocReq</b> member is valid only if the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_infrastructure</b>.</p>
</dd>

### -field <b>bReAssocResp</b>

<dd>
<p>A Boolean value that indicates whether the 802.11 station received an 802.11 Association or
     Reassociation frame from the AP. If <b>TRUE</b>, the 802.11 station received an 802.11 Reassociation Response
     frame from the AP. If <b>FALSE</b>, the 802.11 station received an 802.11 Association Response frame from the
     AP.
     </p>
<p>A value of <b>TRUE</b> for the 
     <b>bReAssocResp</b> member is valid only if the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_infrastructure</b>.</p>
</dd>

### -field <b>uAssocReqOffset</b>

<dd>
<p>The offset of the request frame that is used in the association operation. The frame does not
      include the 802.11 MAC header.</p>
<p>This offset is relative to the start of the buffer that contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.</p>
<p>The Association Request frame that is returned by the miniport driver depends on the setting of the
      IEEE 802.11 
      <b>dot11DesiredBSSType</b> MIB object:</p>
<ul>
<li>
<p>If the 
        <b>dot11DesiredBSSType</b> MIB object is set to dot11_BSS_type_infrastructure, the frame is either the
        802.11 Association Request frame (if 
        <b>bReAssocReq</b> is <b>FALSE</b>) or Reassociation Request frame (if 
        <b>bReAssocReq</b> is <b>TRUE</b>) that was sent to the AP.The miniport driver must return an 802.11 Probe
        Request frame that is either sent by the association initiator or created by the driver based on
        information that was exchanged during the association operation.</p>
</li>
<li>
<p>If the 
        <b>dot11DesiredBSSType</b> MIB object is set to dot11_BSS_type_independent, the miniport driver must
        set the 
        <b>uAssocReqOffset</b> member to zero.</p>
</li>
</ul>
<p>The miniport driver must set the 
      <b>uAssocReqOffset</b> and 
      <b>uAssocReqSize</b> members to zero if it was unable to send a request frame during the association
      operation. For example, if the AP failed the 802.11 Authentication frame that was sent by the 802.11
      station, the miniport driver must set 
      <b>uAssocReqOffset</b> and 
      <b>uAssocReqSize</b> to zero.</p>
</dd>

### -field <b>uAssocReqSize</b>

<dd>
<p>The length of the request frame that is used in the association operation. The length of the frame
     does not include the 802.11 MAC header.
     </p>
<p>If the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_independent</b>, the miniport driver must set the 
     <b>uAssocReqSize</b> member to zero.</p>
</dd>

### -field <b>uAssocRespOffset</b>

<dd>
<p>The offset of the response frame that is used in the association operation. The frame does not
      include the 802.11 MAC header.</p>
<p>This offset is relative to the start of the buffer, which contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.</p>
<p>The association response frame that is returned by the miniport driver depends on the setting of the
      IEEE 802.11 
      <b>dot11DesiredBSSType</b> MIB object:</p>
<ul>
<li>
<p>If the 
        <b>dot11DesiredBSSType</b> MIB object is set to dot11_BSS_type_infrastructure, the frame is either the
        802.11 Association Response frame (if 
        <b>bReAssocReq</b> is <b>TRUE</b>) or Reassociation Response frame (if 
        <b>bReAssocReq</b> is <b>FALSE</b>) that was received from the AP. The miniport driver must return an 802.11
        Probe Response frame that is either sent to the association initiator or created by the driver based
        on information exchanged during the association operation.</p>
</li>
<li>
<p>If the 
        <b>dot11DesiredBSSType</b> MIB object is set to dot11_BSS_type_independent, the miniport driver must
        set the 
        <b>uAssocRespOffset</b> member to zero.</p>
</li>
</ul>
<p>The miniport driver must set the 
      <b>uAssocRespOffset</b> and 
      <b>uAssocRespSize</b> members to zero if it did not receive a response frame during the association
      operation.</p>
</dd>

### -field <b>uAssocRespSize</b>

<dd>
<p>The length of the response frame that is used in the association operation. The length of the frame
      does not include the 802.11 MAC header.</p>
<p>If the 
      <b>dot11DesiredBSSType</b> MIB object is set to 
      <b>dot11_BSS_type_independent</b>, the miniport driver must set the 
      <b>uAssocRespSize</b> member to zero.</p>
</dd>

### -field <b>uBeaconOffset</b>

<dd>
<p>The offset of the last received 802.11 Beacon or Probe Response frames. The miniport driver must
      exclude the 802.11 MAC header for these frames when making the 
      <a href="netvista.ndis_status_dot11_association_completion">
      NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> status indication.</p>
<p>This offset is relative to the start of the buffer, which contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.</p>
<div class="alert"><b>Note</b>  If the authentication algorithm used on the association was Wi-Fi Protected
      Access (WPA) or IEEE 802.11i Robust Security Network Association (RSNA), the miniport driver must
      always return the last received 802.11 Beacon frame and must not set the 
      <b>uBeaconOffset</b> and 
      <b>uBeaconSize</b> members to zero.</div>
<div> </div>
</dd>

### -field <b>uBeaconSize</b>

<dd>
<p>The length of the last received 802.11 Beacon frame. The length of the frame does not include the
     802.11 MAC header.</p>
</dd>

### -field <b>uIHVDataOffset</b>

<dd>
<p>The offset of a block of data in a proprietary format that is defined by the IHV. The IHV can use
      this data block for any purposes that are related to the 
      <a href="netvista.ndis_status_dot11_association_completion">
      NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> status indication.</p>
<p>This offset is relative to the start of the buffer, which contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.</p>
<p>If the miniport driver is not returning IHV data in the 
      <a href="netvista.ndis_status_dot11_association_completion">
      NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> status indication, it must set 
      <b>uIHVDataOffset</b> to zero.</p>
</dd>

### -field <b>uIHVDataSize</b>

<dd>
<p>The length of the block of data that is used by the IHV for the 
     <a href="netvista.ndis_status_dot11_association_completion">
     NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> status indication. If the miniport driver is not
     returning IHV data in this indication, it must set 
     <b>uIHVDataSize</b> to zero.</p>
</dd>

### -field <b>AuthAlgo</b>

<dd>
<p>The authentication algorithm that the 802.11 station resolved with the AP or peer station during
     the association operation. For more information about the data type for the 
     <b>AuthAlgo</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547655">DOT11_AUTH_ALGORITHM</a>.
     </p>
<p>The miniport driver must set this member to zero if 
     <b>uStatus</b> is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</dd>

### -field <b>UnicastCipher</b>

<dd>
<p>The unicast cipher algorithm that the 802.11 station resolved with the AP or peer station during
     the association operation. For more information about the data type for the 
     <b>UnicastCipher</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547672">DOT11_CIPHER_ALGORITHM</a>.
     </p>
<p>The miniport driver must set this member to zero if 
     <b>uStatus</b> is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</dd>

### -field <b>MulticastCipher</b>

<dd>
<p>The multicast cipher algorithm that the 802.11 station resolved with the AP or peer station during
     the association operation. For more information about the data type for the 
     <b>MulticastCipher</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547672">DOT11_CIPHER_ALGORITHM</a>.
     </p>
<p>The miniport driver must set this member to zero if 
     <b>uStatus</b> is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</dd>

### -field <b>uActivePhyListOffset</b>

<dd>
<p>The offset of the list of PHY identifiers (IDs) that the 802.11 station uses to send or receive
      packets on the BSS network connection.</p>
<p>The Extensible Station (ExtSTA) msDot11ActivePhyList MIB object also references the active PHY list.
      For more information about this MIB object, see OID_DOT11_ACTIVE_PHY_LIST.</p>
<p>Entries in the active PHY list can be one of the following values:</p>
<ul>
<li>
<p>A PHY ID that is specified by the ExtSTA 
        <b>msDot11DesiredPhyList</b> MIB object. For more information about this MIB object, see 
        <a href="https://msdn.microsoft.com/library/windows/hardware/ff569144">OID_DOT11_DESIRED_PHY_LIST</a>.</p>
</li>
<li>
<p>DOT11_PHY_ID_ANY. The miniport driver can set an entry to this value if the 
        <b>msDot11ActivePhyList</b> MIB object specifies all of the PHY IDs that are specified by the 
        <b>msDot11DesiredPhyList</b> MIB object. An entry with the value of DOT11_PHY_ID_ANY must be the only
        entry in the active PHY list.</p>
</li>
</ul>
<p>The offset of the active PHY list is relative to the start of the buffer that contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.</p>
<p>The miniport driver must set the 
      <b>uActivePhyListOffset</b> and 
      <b>uActivePhyListSize</b> members to zero if 
      <b>uStatus</b> is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</dd>

### -field <b>uActivePhyListSize</b>

<dd>
<p>The length of the active PHY list. The 
     <b>uActivePhyListSize</b> member must be a multiple of 
     <code>sizeof(ULONG)</code>.</p>
</dd>

### -field <b>bFourAddressSupported</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies that the 802.11 station has associated with an AP
     that supports distribution system (DS) services for ISO Layer 2 bridging on any station in the BSS
     network, including mobile stations and APs. The determination of this support is specific to the
     implementation by the IHV.
     </p>
<p>A miniport driver must set the 
     <b>bFourAddressSupported</b> member to <b>FALSE</b> if any of the following are true:</p>
<ul>
<li>
<p>The IEEE 802.11 
       <b>dot11DesiredBSSType</b> MIB object is set to 
       <b>dot11_BSS_type_independent</b>.</p>
</li>
<li>
<p>The 802.11 station did not associate with an AP that supports DS services or cannot determine
       whether the AP supports DS services.</p>
</li>
<li>
<p>The 
       <b>uStatus</b> member is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</li>
</ul>
</dd>

### -field <b>bPortAuthorized</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies that the 802.11 station has successfully performed
     port authorization during the association operation. Port authorization could be based on either the
     IEEE 802.1X/802.11i standards or a proprietary algorithm that is developed by the IHV.
     </p>
<p>The miniport driver must set 
     <b>bPortAuthorized</b> to <b>FALSE</b> if any of the following are true:</p>
<ul>
<li>
<p>The 802.11 station does not perform port authorization.</p>
</li>
<li>
<p>The 
       <b>uStatus</b> member is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>
</li>
</ul>
<p>For more information about port authorization, see 
     <a href="netvista.port_based_network_access">Port-Based Network
     Access</a>.</p>
</dd>

### -field <b>ucActiveQoSProtocol</b>

<dd>
<p>A flag that specifies the quality of service (QoS) protocol that is currently active for this
     association. This member is either zero (indicating that no QoS protocol is active) or one of the
     following flags:
     </p>
<p></p>
<dl>

### -field <a id="DOT11_QOS_PROTOCOL_FLAG_WMM"></a><a id="dot11_qos_protocol_flag_wmm"></a>DOT11_QOS_PROTOCOL_FLAG_WMM

<dd>
<p>The NIC is using the 802.11 WMM QoS protocol.</p>
</dd>

### -field <a id="DOT11_QOS_PROTOCOL_FLAG_11E"></a><a id="dot11_qos_protocol_flag_11e"></a>DOT11_QOS_PROTOCOL_FLAG_11E

<dd>
<p>The NIC is using the 802.11e QoS protocol.</p>
</dd>
</dl>
</dd>

### -field <b>DSInfo</b>

<dd>
<p>A DOT11_DS_INFO value that specifies whether the 802.11 station is connected to the same DS from
     the previous association operation.
     </p>
<p>The 
     <b>DSInfo</b> member is formatted as a DOT11_DS_INFO enumeration, which specifies the following
     values:</p>
<p></p>
<dl>

### -field <a id="DOT11_DS_CHANGED________"></a><a id="dot11_ds_changed________"></a>DOT11_DS_CHANGED
       

<dd>
<p>The 802.11 station has connected to a new DS after the association operation.</p>
</dd>

### -field <a id="DOT11_DS_UNCHANGED________"></a><a id="dot11_ds_unchanged________"></a>DOT11_DS_UNCHANGED
       

<dd>
<p>The 802.11 station is connected to the same DS from the association operation.</p>
</dd>

### -field <a id="DOT11_DS_UNKNOWN________"></a><a id="dot11_ds_unknown________"></a>DOT11_DS_UNKNOWN
       

<dd>
<p>The miniport driver cannot determine whether the DS has changed after the association
       operation.</p>
</dd>
</dl>
<div class="alert"><b>Note</b>  The miniport driver must set 
     <b>DSInfo</b> to 
     <b>DOT11_DS_UNKNOWN</b> if the 
     <b>dot11DesiredBSSType</b> MIB object is set to 
     <b>dot11_BSS_type_independent</b>.</div>
<div> </div>
</dd>

### -field <b>uEncapTableOffset</b>

<dd>
<p>The offset of the list of IEEE EtherType encapsulations for the BSS association.</p>
<p>This offset is relative to the start of the buffer, which contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure. The value of 
      <b>uEncapTableOffset</b> must be aligned on a 4-byte boundary.</p>
<p>The miniport driver formats each entry in this list as a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff547685">DOT11_ENCAP_ENTRY</a> structure.</p>
<p>For more information about the EtherType encapsulation list, see 
      <a href="netvista.802_11_payload_encapsulation">802.11 Payload
      Encapsulation</a>.</p>
</dd>

### -field <b>uEncapTableSize</b>

<dd>
<p>The length of the EtherType encapsulation list.</p>
</dd>

### -field <b>MulticastMgmtCipher</b>

<dd>
<p>The multicast cipher algorithm the NIC chooses (negotiates) for the association for management frame protection (MFP). If MFP is negotiated, this member should be DOT11_CIPHER_ALGO_BIP. If MFP is not negotiated, this field should be DOT11_CIPHER_ALGO_NONE.</p>
</dd>

### -field <b>uAssocComebackTime</b>

<dd>
<p>When a (re)association fails with 802.11 reason code 30 ("Association request rejected temporarily, try again later.") this member indicates the value of the association comeback time requested by the access point (AP). The 802.11 disassociation reason code is present in the lowest 16 bits of <b>uStatus</b> when responding to an association request.</p>
<p>Windows' auto-connection service will add the AP to a blocked list and not attempt to reconnect for at least the indicated comeback time. The NIC will behave like a regular failed authentication until the next connection sequence is begun. After the indicated timeout(comeback) elapses and the connection process is stopped Windows may either find a better alternate connection or comeback to this connection. This value set in this member should use the time units defined in the 802.11 specification. For example, TU.</p>
</dd>
</dl>

## -remarks
<p>The miniport driver must set the 
    <b>uEncapTableOffset</b> and 
    <b>uEncapTableSize</b> members to zero if any of the following are true:</p>

<p>The BSS association does not require changes to the operating system's default list of EtherType
      encapsulations.</p>

<p>The 
      <b>uStatus</b> member is not set to DOT11_ASSOCIATION_STATUS_SUCCESS.</p>

<p>The Extensible Station (ExtSTA) 
      <b>dot11DesiredBSSType</b> management information base (MIB) object is set to 
      <b>dot11_BSS_type_independent</b>.</p>

<p>For more information about the IEEE 802.11 
    <b>dot11DesiredBSSType</b> MIB object, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569142">OID_DOT11_DESIRED_BSS_TYPE</a>.</p>

<p>For more information about the association operation, see 
    <a href="NULL">Association Operations</a>.</p>

<p>Management Frame Protection is negotiated when an access point (AP) and STA set the Management Frame Protection Capable (MFPC) field to 1 in their respective RSN IEs during the (re)association procedure (i.e. Beacon or Probe Response for AP and (re)association request for STA), and both parties confirm the Management Frame Protection Capable bit set to 1 in the 4-Way Handshake (Messages M2 and M3 of the 802.11i 4-way handshake).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 8 and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547655">DOT11_AUTH_ALGORITHM</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547672">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547685">DOT11_ENCAP_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548681">DOT11_MAC_ADDRESS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563600">NdisMIndicateStatusEx</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_association_completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569102">OID_DOT11_ACTIVE_PHY_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569142">OID_DOT11_DESIRED_BSS_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569144">OID_DOT11_DESIRED_PHY_LIST</a>
</dt>
<dt>OID_DOT11_DESIRED_BSS_TYPE</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
