---
UID: NF.swenum.KsServiceBusEnumCreateRequest
title: KsServiceBusEnumCreateRequest function
author: windows-driver-content
description: The KsServiceBusEnumCreateRequest function services IRP_MJ_CREATE requests for the software bus device interface.
old-location: stream\ksservicebusenumcreaterequest.htm
old-project: stream
ms.assetid: 23a2dd4d-ea30-4646-a4c3-bc90ad60933d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsServiceBusEnumCreateRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsServiceBusEnumCreateRequest
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# KsServiceBusEnumCreateRequest function



## -description
<i>This function is intended for internal use only.</i>
The <b>KsServiceBusEnumCreateRequest</b> function services IRP_MJ_CREATE requests for the software bus device interface. 


## -syntax

````
NTSTATUS KsServiceBusEnumCreateRequest(
  _In_    PDEVICE_OBJECT DeviceObject,
  _Inout_ PIRP           Irp
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object.

### -param Irp [in, out]

Pointer to the IRP that is associated with the device object.

## -returns
Returns STATUS_SUCCESS if successful. Otherwise. it returns STATUS_OBJECT_NAME_NOT_FOUND if the IRP's <i>FileObject-&gt;FileName</i> is <b>NULL</b> or if the reference string cannot be located. Otherwise, an appropriate error returns.

## -remarks
<b>KsServiceBusEnumCreateRequest</b> services the IRP_MJ_CREATE request for the registered device interface by matching the given IRP's<i> FileObject-&gt;FileName</i> with the registered bus reference strings. If the device reference is present, enumerated and created, the IRP is simply re-routed to the actual device. If the reference string is <b>NULL</b>, it is assumed that this is a request for the bus interface and the IRP_MJ_CREATE is completed. If the device reference has not already been enumerated, or is not active, the IRP is queued and a PDO is created and a bus enumeration is initiated by IoInvalidateDeviceRelations().

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Swenum.h (include Swenum.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksservicebusenumpnprequest">KsServiceBusEnumPnpRequest</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsServiceBusEnumCreateRequest function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
