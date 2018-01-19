---
UID : NS:windot11._DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
title : _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
author : windows-driver-content
description : The response parameters for a provision discovery response are specified in a DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE request to the miniport.
old-location : netvista\dot11_received_provision_discovery_response_parameters.htm
old-project : netvista
ms.assetid : 5D084A9F-B0B1-4DB6-91CF-8185063A1D65
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
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
req.alt-api : DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
req.alt-loc : Windot11.h
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
req.typenames : DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
req.product : Windows 10 or later.
---

# _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure


## Syntax
````
typedef struct _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS;
````

## Members

        
            `BSSID`

            The BSSID from the received provision discovery response packet.
        
            `DialogToken`

            The dialog token from the received provision discovery response packet.
        
            `Header`

            The type, revision, and size of the <b>DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
        
            `TransmitterDeviceAddress`

            The address of the device that transmitted the provision discovery response packet.
        
            `uIEsLength`

            The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.
        
            `uIEsOffset`

            The offset, in bytes,  of the array of additional information elements (IEs) received in the provision discovery response packet. This offset is from the start of the buffer that contains this structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Windot11.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451808">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>