---
UID: NS.NDISWWAN._NDIS_WWAN_HOME_PROVIDER
title: _NDIS_WWAN_HOME_PROVIDER
author: windows-driver-content
description: The NDIS_WWAN_HOME_PROVIDER structure represents details about the home network provider.
old-location: netvista\ndis_wwan_home_provider.htm
old-project: netvista
ms.assetid: 5f92a711-97fe-4420-be50-89302cc9486c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_WWAN_HOME_PROVIDER, *PNDIS_WWAN_HOME_PROVIDER, NDIS_WWAN_HOME_PROVIDER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_HOME_PROVIDER
req.alt-loc: ndiswwan.h
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

# _NDIS_WWAN_HOME_PROVIDER structure



## -description
The NDIS_WWAN_HOME_PROVIDER structure represents details about the home network provider.



## -syntax

````
typedef struct _NDIS_WWAN_HOME_PROVIDER {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_PROVIDER      Provider;
} NDIS_WWAN_HOME_PROVIDER, *PNDIS_WWAN_HOME_PROVIDER;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_HOME_PROVIDER structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
 NDIS_WWAN_HOME_PROVIDER_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_HOME_PROVIDER)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the home provider operation. The following table shows the possible values for this
     member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
Home provider operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
Home provider operation failed because the device requires a PIN.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
Home provider operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_READ_FAILURE

</td>
<td>
Home provider operation failed because the information could not be read from the device or SIM
        card. The error may be returned in instances where the SIM card does not have home provider
        information provisioned.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
</table>
 


### -field Provider

A formatted 
     <a href="netvista.wwan_provider2">WWAN_PROVIDER2</a> object that represents details
     about a network provider.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.wwan_provider2">WWAN_PROVIDER2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_HOME_PROVIDER structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

