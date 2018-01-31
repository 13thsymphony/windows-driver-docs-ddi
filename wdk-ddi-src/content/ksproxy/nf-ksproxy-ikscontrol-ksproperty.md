---
UID : NF:ksproxy.IKsControl.KsProperty
title : IKsControl::KsProperty method
author : windows-driver-content
description : The KsProperty method sets a property or retrieves property information, along with any other defined support operations available on a property set.
old-location : stream\ikscontrol_ksproperty.htm
old-project : stream
ms.assetid : cc43f704-e1f8-4d62-8cdf-11575ec0b473
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IKsControl::KsProperty, KsProperty method [Streaming Media Devices], KsProperty method [Streaming Media Devices], IKsControl interface, IKsControl, IKsControl interface [Streaming Media Devices], KsProperty method, ksproxy_463b7e97-4356-4d2e-b005-6f81219bda64.xml, KsProperty, stream.ikscontrol_ksproperty, ksproxy/IKsControl::KsProperty
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : DesktopMobile
req.target-min-winverclnt : 
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
req.lib : ksproxy.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
---


# KsProperty method
The <b>KsProperty</b> method sets a property or retrieves property information, along with any other defined support operations available on a property set.

## Syntax

````
HRESULT KsProperty(
  [in]      PKSPROPERTY Property,
  [in]      ULONG       PropertyLength,
  [in, out] LPVOID      PropertyData,
  [in]      ULONG       DataLength,
  [in, out] ULONG       *BytesReturned
);
````

## Parameters

`Property`

Pointer to a structure that describes a property and the request type of the property request. This structure must be either a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> or a structure that contains a <b>KSPROPERTY</b> structure as its first member. An example of a structure that can be pointed to by this member is the <a href="..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_s.md">KSPROPERTY_VIDEOPROCAMP_S</a> structure.

`PropertyLength`

Size, in bytes, of the buffer at <i>Property</i>.

`PropertyData`

Pointer to a buffer that contains data for a KSPROPERTY_TYPE_SET, KSPROPERTY_TYPE_UNSERIALIZESET, or KSPROPERTY_TYPE_UNSERIALIZERAW operation, or buffer space that receives data for all other operations.

`DataLength`

Size, in bytes, of the buffer at <i>PropertyData</i>.

`BytesReturned`

Pointer to a variable that receives the size, in bytes, of the data that <b>KsProperty</b> stores in the buffer at <i>PropertyData</i>. If no data is stored, the size is zero.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

To determine the buffer size that is required for a specific property request, you can call this method with <i>PropertyData</i> set to <b>NULL</b> and <i>DataLength</i> equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA), and <i>BytesReturned</i> contains the size of the required buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | DesktopMobile |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_s.md">KSPROPERTY_VIDEOPROCAMP_S</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsProperty method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>