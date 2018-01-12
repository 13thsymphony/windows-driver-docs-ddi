---
UID: NF:swenum.KsDereferenceSoftwareBusObject
title: KsDereferenceSoftwareBusObject function
author: windows-driver-content
description: The KsDereferenceSoftwareBusObject function decrements the reference count of the demand-load bus enumerator object's PDO.
old-location: stream\ksdereferencesoftwarebusobject.htm
old-project: stream
ms.assetid: 11203a5d-1484-4a49-aedc-e11baf22cac9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsDereferenceSoftwareBusObject
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
req.alt-api: KsDereferenceSoftwareBusObject
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
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsDereferenceSoftwareBusObject function



## -description
<i>This function is intended for internal use only.</i>

The <b>KsDereferenceSoftwareBusObject</b> function decrements the reference count of the demand-load bus enumerator object's PDO. 



## -syntax

````
VOID KsDereferenceSoftwareBusObject(
  _In_ KSDEVICE_HEADER Header
);
````


## -parameters

### -param Header [in]

Pointer to the device header (extension) of the demand-load bus enumerator.


## -returns
None


## -remarks
A minidriver can access this function through the <b>DereferenceDeviceObject</b> member of the BUS_INTERFACE_SWENUM structure.

When the demand-load bus enumerator object's PDO reference count is 0, it becomes eligible for removal. Note that this condition does not guarantee removal.


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
<a href="..\swenum\ns-swenum-_bus_interface_swenum.md">BUS_INTERFACE_SWENUM</a>
</dt>
<dt>
<a href="..\swenum\nf-swenum-ksreferencesoftwarebusobject.md">KsReferenceSoftwareBusObject</a>
</dt>
<dt>
<a href="..\swenum\nf-swenum-ksquerysoftwarebusinterface.md">KsQuerySoftwareBusInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDereferenceSoftwareBusObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

