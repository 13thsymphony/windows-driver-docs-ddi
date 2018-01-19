---
UID : NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
title : _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
author : windows-driver-content
description : The NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure represents device service session data that has been read by the miniport driver from the MB device.
old-location : netvista\ndis_wwan_device_service_session_read.htm
old-project : netvista
ms.assetid : 6417E9B6-FDF9-4353-A966-1AFCB14A2735
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndiswwan.h
req.include-header : Ndiswwan.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
req.alt-loc : ndiswwan.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure
The NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure represents device service session data that has been read by the miniport driver from the MB device.

## Syntax
````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ {
  NDIS_OBJECT_HEADER               Header;
  WWAN_DEVICE_SERVICE_SESSION_READ ReadData;
} NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ;
````

## Members

        
            `Header`

            The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_DEVICE_SERVICE_SESSION_READ_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_READ)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.
        
            `ReadData`

            The data that has been read from a device service session.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_device_service_session_read.md">WWAN_DEVICE_SERVICE_SESSION_READ</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>