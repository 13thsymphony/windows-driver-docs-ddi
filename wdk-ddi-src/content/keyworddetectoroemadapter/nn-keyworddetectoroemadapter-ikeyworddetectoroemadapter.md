---
UID: NN.keyworddetectoroemadapter.IKeywordDetectorOemAdapter
title: IKeywordDetectorOemAdapter
author: windows-driver-content
description: IKeywordDetectorOemAdapter is a Component Object Model (COM) interface for interacting with the Voice Activation Driver Interface. The IKeywordDetectorOemAdapter interface is supported in Windows 10 and later versions of Windows.
old-location: audio\ikeyworddetectoroemadapter.htm
old-project: audio
ms.assetid: FB243792-C0B0-4BCA-B4C4-B6E17FDB615C
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: __MIDL_IKeywordDetectorOemAdapter_0002, KEYWORDID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKeywordDetectorOemAdapter
req.alt-loc: keyworddetectoroemadapter.h
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
---

# IKeywordDetectorOemAdapter interface



## -description
<b>IKeywordDetectorOemAdapter</b> is a Component Object Model (COM) interface for interacting with the Voice Activation Driver Interface. The <b>IKeywordDetectorOemAdapter</b> interface is supported 
in Windows 10 and later versions of Windows.

 The OEM supplies a COM object implementation that acts as an intermediary between the operating system  and the driver, helping to
 compute or parse the opaque data that is written and read to the audio driver through <a href="https://msdn.microsoft.com/library/windows/hardware/dn932151">KSPROPERTY_SOUNDDETECTOR_PATTERNS</a> and
  <a href="https://msdn.microsoft.com/library/windows/hardware/dn932150">KSPROPERTY_SOUNDDETECTOR_MATCHRESULT</a>.


The class identifier (CLSID) of the COM object is a detector pattern type GUID 
returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn932152">KSPROPERTY_SOUNDDETECTOR_SUPPORTEDPATTERNS</a>. The operating system calls <a href="com.cocreateinstance">CoCreateInstance</a> passing the pattern type GUID to instantiate the appropriate COM object that is compatible with keyword pattern type and calls methods on the object’s <b>IKeywordDetectorOemAdapter</b> interface.
The operating supplies a proxy-stub for <b>IKeywordDetectorOemAdapter</b>. The OEM’s implementation may choose any of the COM threading models. 

The interface design attempts to keep the object implementation stateless. In other words, the implementation should require no state to be stored between method calls. 
In fact, internal C++ classes likely do not need any member variables beyond those required to implement a COM object in general.




## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKeywordDetectorOemAdapter</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Keyworddetectoroemadapter.h</dt>
</dl>
</td>
</tr>
</table>