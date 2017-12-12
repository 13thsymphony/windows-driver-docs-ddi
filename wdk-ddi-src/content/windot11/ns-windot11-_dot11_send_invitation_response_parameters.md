---
UID: NS.WINDOT11._DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
title: _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
author: windows-driver-content
description: The parameters for a response to a invitation request are specified in a DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_INVITATION_RESPONSE request to the miniport.
old-location: netvista\dot11_send_invitation_response_parameters.htm
old-project: netvista
ms.assetid: 0A041372-7EC0-44E3-AD1F-3EA0CBB21425
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, *PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
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
req.product: Windows 10 or later.
---

# _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER              Header;
  DOT11_MAC_ADDRESS               ReceiverDeviceAddress;
  DOT11_DIALOG_TOKEN              DialogToken;
  PVOID                           RequestContext;
  ULONG                           uSendTimeout;
  DOT11_WFD_STATUS_CODE           Status;
  DOT11_WFD_CONFIGURATION_TIMEOUT MinimumConfigTimeout;
  DOT11_MAC_ADDRESS               GroupBSSID;
  BOOLEAN                         bUseGroupBSSID;
  DOT11_WFD_CHANNEL               OperatingChannel;
  BOOLEAN                         bUseSpecifiedOperatingChannel;
  ULONG                           uIEsOffset;
  ULONG                           uIEsLength;
} DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, *PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS;
````


## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_SEND_INVITATION_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_SEND_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field ReceiverDeviceAddress

The sender address received from the invitation request packet. This is the device address where the invitation response will be sent.


### -field DialogToken

The dialog token received from the invitation request packet. This dialog token will be used in  the invitation response  packet.


### -field RequestContext

Miniport context data included in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439793">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a> indication.


### -field uSendTimeout

The maximum time, in milliseconds, allowed to send the invitation response. If the timeout expires before the miniport has successfully transmitted the provision discovery response, it should indicate the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439781">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a> with a failure status.


### -field Status

Status information to include in the invitation response.


### -field MinimumConfigTimeout

The configuration timeout required by the system  to change its mode of operation to a Peer-to-Peer (P2P) Group Owner or a P2P Client. The miniport driver can set this with a larger value if necessary.


### -field GroupBSSID

The BSSID used by the P2P Group Owner for its P2P Group.


### -field bUseGroupBSSID

If TRUE, the BSSID in <b>GroupBSSID</b> is included in the invitation response. Otherwise, <b>GroupBSSID</b> is not valid.


### -field OperatingChannel

The channel information to include in the Operating Channel attribute of the invitation response.


### -field bUseSpecifiedOperatingChannel

If TRUE, the operatin channel specified in <b>OperatingChannel</b> is included in the invitation response. Otherwise, the miniport driver may choose its own operating channel if <b>Status</b> == <b>DOT11_WFD_STATUS_SUCCESS</b>. If <b>Status</b> != <b>DOT11_WFD_STATUS_SUCCESS</b>, the miniport must not include the operating channel attribute in the inivitation response. 


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) the Wi-Fi Direct (WFD) port must add to the invitation response packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439781">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439793">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451807">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

