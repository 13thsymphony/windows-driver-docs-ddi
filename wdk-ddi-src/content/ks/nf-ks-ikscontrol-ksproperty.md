---
UID: NF:ks.IKsControl.KsProperty
title: IKsControl::KsProperty method
author: windows-driver-content
description: The IKsControl::KsProperty method sets a property or retrieves property information, together with any other defined support operations available on a property set.
old-location: stream\ikscontrol_ksproperty2.htm
old-project: stream
ms.assetid: a80312ef-394a-4a59-8a04-35d7c60689b6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsControl, IKsControl::KsProperty, KsProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsControl.KsProperty
req.alt-loc: ks.h
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
req.typenames: 
---

# IKsControl::KsProperty method



## -description
The <b>IKsControl::KsProperty</b> method sets a property or retrieves property information, together with any other defined support operations available on a property set. 



## -syntax

````
NTSTATUS KsProperty(
  [in]      PKSPROPERTY Property,
  [in]      ULONG       PropertyLength,
  [in, out] PVOID       PropertyData,
  [in]      ULONG       DataLength,
  [out]     ULONG       *BytesReturned
);
````


## -parameters

### -param Property [in]

Pointer to a structure that describes a property and the request type of the property request. This structure must be either a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> or a structure that contains a <b>KSPROPERTY</b> structure as its first member. An example of a structure that can be pointed to by this member is the <a href="..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_s.md">KSPROPERTY_VIDEOPROCAMP_S</a> structure.


### -param PropertyLength [in]

Specifies size, in bytes, of the buffer at <i>Property</i>.


### -param PropertyData [in, out]

Pointer to a buffer that contains data for a KSPROPERTY_TYPE_SET, KSPROPERTY_TYPE_UNSERIALIZESET, or KSPROPERTY_TYPE_UNSERIALIZERAW operation, or buffer space that receives data for all other operations.


### -param DataLength [in]

Specifies size, in bytes, of the buffer at <i>PropertyData</i>.


### -param BytesReturned [out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsProperty</b> stores in the buffer at <i>PropertyData</i>. If no data is stored, the size is zero.


## -returns
The <b>IKsControl::KsProperty</b> method returns the same value that would be returned if the property had been sent by IOCTL.


## -remarks
To determine the buffer size that is required for a specific property request, you can call this method with <i>PropertyData</i> set to <b>NULL</b> and <i>DataLength</i> equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA), and <i>BytesReturned</i> contains the size of the required buffer.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
<dt>Mobile</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsProperty method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

