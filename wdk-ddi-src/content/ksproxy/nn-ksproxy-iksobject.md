---
UID: NN.ksproxy.IKsObject
title: IKsObject
author: windows-driver-content
description: The IKsObject interface provides a method to retrieve the file handle of a KS object.
old-location: stream\iksobject.htm
old-project: stream
ms.assetid: c4422564-3fc0-4087-b628-056488c723e6
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
req.alt-api: IKsObject
req.alt-loc: ksproxy.h,ksproxy.h.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksproxy.h
req.dll: 
req.irql: 
---

# IKsObject interface



## -description
The <b>IKsObject</b> interface provides a method to retrieve the file handle of a KS object. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsObject</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsObject</b> also has these types of members:

The <b>IKsObject</b> interface has these methods.

Retrieves the file handle of a KS object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsObject</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsObject</b> also has these types of members:

The <b>IKsObject</b> interface has these methods.

Retrieves the file handle of a KS object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsObject</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsObject</b> also has these types of members:

The <b>IKsObject</b> interface has these methods.

Retrieves the file handle of a KS object.

 


## -members
The <b>IKsObject</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="stream.iksobject_ksgetobjecthandle">KsGetObjectHandle</a>
</td>
<td align="left" width="63%">
Retrieves the file handle of a KS object.

</td>
</tr>
</table>Retrieves the file handle of a KS object.

 


## -remarks
The IID for this interface is IID_IKsObject.

<b>IKsObject</b> is defined in <i>Ksproxy.h</i> within the #ifdef __STREAMS__ section.

__STREAMS__ is defined in <i>Stream.h</i>, a header from the DirectX SDK.


## -requirements
<table>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ksproxy.h</dt>
</dl>
</td>
</tr>
</table>