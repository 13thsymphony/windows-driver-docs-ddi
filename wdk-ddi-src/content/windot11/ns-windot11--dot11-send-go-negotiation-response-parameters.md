---
UID: NS.windot11._DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS
title: DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS
author: windows-driver-content
description: The parameters for a response to a Group Owner (GO) negotiation request are specified in a DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_INVITATION_RESPONSE request to the miniport.
old-location: netvista\dot11_send_go_negotiation_response_parameters.htm
old-project: netvista
ms.assetid: F5EC240C-6438-477C-A5D3-B018B52AC4F0
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS
req.alt-loc: Windot11.h
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

# DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER              Header;
  DOT11_MAC_ADDRESS               PeerDeviceAddress;
  DOT11_DIALOG_TOKEN              DialogToken;
  PVOID                           ResponseContext;
  ULONG                           uSendTimeout;
  DOT11_WFD_STATUS_CODE           Status;
  DOT11_WFD_GO_INTENT             GroupOwnerIntent;
  DOT11_WFD_CONFIGURATION_TIMEOUT MinimumConfigTimeout;
  DOT11_MAC_ADDRESS               IntendedInterfaceAddress;
  DOT11_WFD_GROUP_CAPABILITY      GroupCapability;
  DOT11_WFD_GROUP_ID              GroupID;
  BOOLEAN                         bUseGroupID;
  ULONG                           uIEsOffset;
  ULONG                           uIEsLength;
} DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS, *PDOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the <b>DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.</p>
<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>PeerDeviceAddress</b>

<dd>
<p>The Peer-to-Peer (P2P) address of the Wi-Fi Direct (WFD) device that originated the GO negotiation request.</p>
</dd>

### -field <b>DialogToken</b>

<dd>
<p>The dialog token received from the GO negotiation request packet. This dialog token must be included in  the GO negotiation response  packet.</p>
</dd>

### -field <b>ResponseContext</b>

<dd>
<p>Miniport context data included in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439789">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_REQUEST</a> indication.</p>
</dd>

### -field <b>uSendTimeout</b>

<dd>
<p>The maximum time, in milliseconds, allowed to send the GO negotiation response. If the time-out expires before the miniport has successfully transmitted the GO negotiation response, it should indicate the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439776">NDIS_STATUS_DOT11_WFD_GO_NEGOTIATION_RESPONSE_SEND_COMPLETE</a> with a failure status.</p>
</dd>

### -field <b>Status</b>

<dd>
<p>The status information to include in the GO  negotiation response.</p>
</dd>

### -field <b>GroupOwnerIntent</b>

<dd>
<p>The value for GO intent. This should be included in the Group Owner Intent attribute of the GO negotiation request.</p>
</dd>

### -field <b>MinimumConfigTimeout</b>

<dd>
<p>The configuration time-out required by the system  to change its mode of operation to a P2P Group Owner or a P2P Client. The miniport driver can set this with a larger value if necessary.</p>
</dd>

### -field <b>IntendedInterfaceAddress</b>

<dd>
<p>The P2P interface address that is intended for the P2P group.</p>
</dd>

### -field <b>GroupCapability</b>

<dd>
<p>The capability values that are included in the Group Capability bitmask of the P2P Capability Information Element (IE) in  the GO negotiation response.</p>
</dd>

### -field <b>GroupID</b>

<dd>
<p>The group identifier to include in the Group ID attribute of the GO negotiation response.</p>
</dd>

### -field <b>bUseGroupID</b>

<dd>
<p>If TRUE, the value in <b>GroupID</b> should be included in the GO negotiation response.</p>
</dd>

### -field <b>uIEsOffset</b>

<dd>
<p>The offset, in bytes,  of the array of additional IEs that the Wi-Fi Direct (WFD) port must add to the GO negotiation response packet. This offset is from the start of the buffer that contains this structure.</p>
</dd>

### -field <b>uIEsLength</b>

<dd>
<p>The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with   Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439789">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451807">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SEND_GO_NEGOTIATION_RESPONSE_PARAMETERS structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
