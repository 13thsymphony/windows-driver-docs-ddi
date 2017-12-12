---
UID: NF.ucmtypes.UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG
title: UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG function
author: windows-driver-content
description: Initializes a UCM_PD_REQUEST_DATA_OBJECT structure by interpreting Request Data Object values and sets each field correctly.
old-location: buses\ucm_pd_request_data_object_init_ulong.htm
old-project: usbref
ms.assetid: 825AA3FC-1D2E-4D71-8F21-C89A249B3F1A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG
req.alt-loc: Ucmtypes.h
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

# UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG function



## -description
Initializes a <a href="buses.ucm_pd_request_data_object">UCM_PD_REQUEST_DATA_OBJECT</a>  structure by interpreting Request Data Object values and sets each field correctly.




## -syntax

````
void UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG(
  _Out_ PUCM_PD_REQUEST_DATA_OBJECT Pdo,
  _In_  ULONG                       UlongInLittleEndian
);
````


## -parameters

### -param Pdo [out]

A pointer to a <a href="buses.ucm_pd_request_data_object">UCM_PD_REQUEST_DATA_OBJECT</a> structure.


### -param UlongInLittleEndian [in]

The ULONG value to set in the <b>Ul</b> member of   <a href="buses.ucm_pd_request_data_object">UCM_PD_REQUEST_DATA_OBJECT</a>.


## -returns
This function does not return a value.


## -remarks
For information about Request Data Objects, see the Power Delivery specification. There are different types of Request Data Objects and the type depends on the Power Data Object that is specified in the <b>ObjectPosition</b> member of <a href="buses.ucm_pd_request_data_object">UCM_PD_REQUEST_DATA_OBJECT</a>. The  source buffer is little-endian format and the client driver can memcopy the Request Data Objects from the hardware into an array of <b>UCM_PD_REQUEST_DATA_OBJECT</b> structures.
 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmtypes.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ucm_pd_request_data_object">UCM_PD_REQUEST_DATA_OBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

