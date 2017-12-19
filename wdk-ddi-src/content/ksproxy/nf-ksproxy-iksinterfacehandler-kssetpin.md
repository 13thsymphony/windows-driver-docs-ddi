---
UID: NF.ksproxy.IKsInterfaceHandler.KsSetPin
title: IKsInterfaceHandler::KsSetPin method
author: windows-driver-content
description: The KsSetPin method informs the streaming interface handler about the pin with which to communicate when passing data.
old-location: stream\iksinterfacehandler_kssetpin.htm
old-project: stream
ms.assetid: 71e4be0a-a5a6-469a-948b-bc5277bc8cbe
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsInterfaceHandler, IKsInterfaceHandler::KsSetPin, KsSetPin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsInterfaceHandler.KsSetPin
req.alt-loc: ksproxy.h
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
---

# IKsInterfaceHandler::KsSetPin method



## -description
The <b>KsSetPin</b> method informs the streaming interface handler about the pin with which to communicate when passing data.



## -syntax

````
HRESULT KsSetPin(
  [in] IKsPin *KsPin
);
````


## -parameters

### -param KsPin [in]

Pointer to the <a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a> interface for the pin to which this streaming interface handler is to be attached. This pin must support the <a href="..\ksproxy\nn-ksproxy-iksobject.md">IKsObject</a> interface from which the underlying kernel handle can be obtained.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
The <b>KsSetPin</b> method is called after an instance of the interface handler is created but before any streaming is required of the instance.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksobject.md">IKsObject</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsInterfaceHandler::KsSetPin method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

