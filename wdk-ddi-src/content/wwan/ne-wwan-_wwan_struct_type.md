---
UID: NE.wwan._WWAN_STRUCT_TYPE
title: _WWAN_STRUCT_TYPE
author: windows-driver-content
description: The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the WWAN_LIST_HEADER object in memory.
old-location: netvista\wwan_struct_type.htm
old-project: netvista
ms.assetid: 43729964-9338-45ab-ad59-406176c1ae9f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_STRUCT_TYPE, *PWWAN_STRUCT_TYPE, WWAN_STRUCT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_STRUCT_TYPE
req.alt-loc: wwan.h
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

# _WWAN_STRUCT_TYPE enumeration



## -description
The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the
  WWAN_LIST_HEADER object in memory.



## -syntax

````
typedef enum _WWAN_STRUCT_TYPE { 
  WwanStructTN                      = 0,
  WwanStructContext,
  WwanStructProvider,
  WwanStructSmsPdu,
  WwanStructReserved0,
  WwanStructReserved1,
  WwanStructReserved2,
  WwanStructSmsCdma,
  WwanStructReserved3,
  WwanStructDeviceServiceEntry,
  WwanStructProvider2,
  WwanStructDeviceServiceGuid,
  WwanStructDeviceServiceCommandId,
  WwanStructDeviceCellularClass,
  WwanStructMax
} WWAN_STRUCT_TYPE, *PWWAN_STRUCT_TYPE;
````


## -enum-fields

### -field WwanStructTN

The elements are NULL-terminated strings of Telephone Number (TNs), with each string having
     WWAN_TN_LEN characters.
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a> uses this value to
     represent a list of TNs assigned to the device.


### -field WwanStructContext

The elements are of type 
     <a href="netvista.wwan_context">WWAN_CONTEXT</a>.
     


<a href="netvista.oid_wwan_provisioned_contexts">
     OID_WWAN_PROVISIONED_CONTEXTS</a> uses this value to represent a list of provisioned
     contexts.


### -field WwanStructProvider

The elements are of type 
     <a href="netvista.wwan_provider">WWAN_PROVIDER</a>.
     

Both <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a> and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a> use this
     value to represent a list of network providers for WWAN 1.0 miniport drivers.


### -field WwanStructSmsPdu

The elements are of type 
     <a href="netvista.wwan_sms_pdu_record">WWAN_SMS_PDU_RECORD</a>.


### -field WwanStructReserved0

The value is reserved for future use. Do not use.


### -field WwanStructReserved1

The value is reserved for future use. Do not use.


### -field WwanStructReserved2

The value is reserved for future use. Do not use.


### -field WwanStructSmsCdma

The elements are of type 
     <a href="netvista.wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>.


### -field WwanStructReserved3

The value is reserved for future use. Do not use.


### -field WwanStructDeviceServiceEntry

The elements are of type 
     <a href="netvista.wwan_device_service_entry">WWAN_DEVICE_SERVICE_ENTRY</a>.


### -field WwanStructProvider2

The elements are of type 
     <a href="netvista.wwan_provider2">WWAN_PROVIDER2</a>.

The following OIDs use this value to represent a list of network providers for WWAN 2.0 miniport drivers:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831868">OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS</a>



### -field WwanStructDeviceServiceGuid

The elements are of type 
     GUID.


### -field WwanStructDeviceServiceCommandId

The elements are of type ULONG.


### -field WwanStructDeviceCellularClass

The elements are of type <a href="netvista.wwan_cellular_class">WWAN_CELLULAR_CLASS</a>. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569824">OID_WWAN_DEVICE_CAPS</a> uses this value to represent multiple cellular classes supported by the miniport driver.


### -field WwanStructMax

The total number of supported types.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 8 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_context">WWAN_CONTEXT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569831">OID_WWAN_PROVISIONED_CONTEXTS</a>
</dt>
<dt>
<a href="netvista.wwan_provider">WWAN_PROVIDER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>
</dt>
<dt>
<a href="netvista.wwan_sms_pdu_record">WWAN_SMS_PDU_RECORD</a>
</dt>
<dt>
<a href="netvista.wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>
</dt>
<dt>
<a href="netvista.wwan_list_header">WWAN_LIST_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_STRUCT_TYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

