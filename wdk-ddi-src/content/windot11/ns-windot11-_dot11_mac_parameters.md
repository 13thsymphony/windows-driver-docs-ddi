---
UID: NS:windot11._DOT11_MAC_PARAMETERS
title: "_DOT11_MAC_PARAMETERS"
author: windows-driver-content
description: The DOT11_MAC_PARAMETERS is the optional input for an OID_DOT11_CREATE_MAC request. The device role is defined in an operation mode bitmask included in this structure.
old-location: netvista\dot11_mac_parameters.htm
old-project: netvista
ms.assetid: 53114ABE-33F2-4DA2-ABE0-2547547AA6AD
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11_MAC_PARAMETERS structure [Network Drivers Starting with Windows Vista], windot11/PDOT11_MAC_PARAMETERS, Type, Revision, *PDOT11_MAC_PARAMETERS, DOT11_MAC_PARAMETERS, netvista.dot11_mac_parameters, PDOT11_MAC_PARAMETERS, windot11/DOT11_MAC_PARAMETERS, PDOT11_MAC_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], Size, _DOT11_MAC_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Windot11.h
apiname:
-	DOT11_MAC_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDOT11_MAC_PARAMETERS, DOT11_MAC_PARAMETERS"
req.product: Windows 10 or later.
---

# _DOT11_MAC_PARAMETERS structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_MAC_PARAMETERS</b> is the optional input for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff569124">OID_DOT11_CREATE_MAC</a> request. The device role is defined in an operation mode bitmask included in this structure.

## Syntax
````
typedef struct _DOT11_MAC_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              uOpmodeMask;
} DOT11_MAC_PARAMETERS, *PDOT11_MAC_PARAMETERS;
````

## Members


`Header`

The object header identifying the type and revision of this structure. The required member settings of <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> are the following:



#### Type

Must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>



#### Revision

Must be set to <b>DOT11_MAC_PARAMETERS_REVISION_1</b>



#### Size

Must be set to <b>DOT11_SIZEOF_MAC_PARAMETERS_REVISION_1</b>

`uOpmodeMask`

A bitwise OR value of the operation modes Windows may set for the created port. This bitmask is defined through the following:





#### DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode.



#### DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.



#### DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 Versions:\_Supported in Windows 8 |
| **Header** | windot11.h (include Windot11.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569124">OID_DOT11_CREATE_MAC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>