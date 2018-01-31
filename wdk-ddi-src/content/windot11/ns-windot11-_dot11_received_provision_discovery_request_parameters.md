---
UID : NS:windot11._DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS
title : "_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS"
author : windows-driver-content
description : The parameters for a provision discovery request are specified in a DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure. This structure is sent with an NDIS_STATUS_DOT11_WFD_RECEIVED_PROVISION_DISCOVERY_REQUEST indication.
old-location : netvista\dot11_received_provision_discovery_request_parameters.htm
old-project : netvista
ms.assetid : 1F6D8F31-D813-4CC3-BBA1-167560436AD6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, windot11/DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, windot11/PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure [Network Drivers Starting with Windows Vista], netvista.dot11_received_provision_discovery_request_parameters
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Windot11.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with   Windows 8.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS
req.product : Windows 10 or later.
---

# _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for a provision discovery request are specified in a <b>DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439797">NDIS_STATUS_DOT11_WFD_RECEIVED_PROVISION_DISCOVERY_REQUEST</a> indication.

## Syntax
````
typedef struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  PVOID              RequestContext;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS;
````

## Members


`BSSID`

The BSSID in the received provision discovery request packet.

`DialogToken`

The dialog token received  in the provision discovery request packet.

`Header`

The type, revision, and size of the <b>DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.
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
<td>DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
</table>

`RequestContext`

The context data from the miniport. The system will send this data with angiven initially by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451808">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a> request.

`TransmitterDeviceAddress`

The address of the device that transmitted the provision discovery request packet.

`uIEsLength`

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.

`uIEsOffset`

The offset, in bytes,  of the array of additional information elements (IEs) received in the provision discovery request packet. This offset is from the start of the buffer that contains this structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Windot11.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439797">NDIS_STATUS_DOT11_WFD_RECEIVED_PROVISION_DISCOVERY_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451808">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>