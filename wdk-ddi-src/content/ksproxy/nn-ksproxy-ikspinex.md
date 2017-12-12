---
UID: NN.ksproxy.IKsPinEx
title: IKsPinEx
author: windows-driver-content
description: The IKsPinEx interface inherits all the methods of the IKsPin interface and extends IKsPin to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.
old-location: stream\ikspinex.htm
old-project: stream
ms.assetid: 9e6fd96d-c78e-44f3-ae4c-3688da48a494
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsSynchronousDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPinEx
req.alt-loc: Ksproxy.lib,Ksproxy.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
---

# IKsPinEx interface



## -description
The <b>IKsPinEx</b> interface inherits all the methods of the <b>IKsPin</b> interface and extends <b>IKsPin</b> to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.

The IID for this interface is IID_IKsPinEx.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinEx</b> interface inherits from <a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a>. <b>IKsPinEx</b> also has these types of members:

The <b>IKsPinEx</b> interface has these methods.

Notifies the filter graph of an error to give the filter graph an opportunity to halt.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinEx</b> interface inherits from <a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a>. <b>IKsPinEx</b> also has these types of members:

The <b>IKsPinEx</b> interface has these methods.

Notifies the filter graph of an error to give the filter graph an opportunity to halt.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinEx</b> interface inherits from <a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a>. <b>IKsPinEx</b> also has these types of members:

The <b>IKsPinEx</b> interface has these methods.

Notifies the filter graph of an error to give the filter graph an opportunity to halt.

 


## -members
The <b>IKsPinEx</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="stream.ikspinex_ksnotifyerror">KsNotifyError</a>
</td>
<td align="left" width="63%">
Notifies the filter graph of an error to give the filter graph an opportunity to halt.

</td>
</tr>
</table>Notifies the filter graph of an error to give the filter graph an opportunity to halt.

 


## -remarks
An interface handler (<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>) uses many of the <b>IKsPinEx</b> methods to route media samples of a particular media type. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksproxy.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ksproxy.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspin~r1.md">IKsPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinEx interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

