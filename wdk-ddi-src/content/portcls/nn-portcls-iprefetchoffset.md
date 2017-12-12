---
UID: NN.portcls.IPreFetchOffset
title: IPreFetchOffset
author: windows-driver-content
description: The IPreFetchOffset interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream.
old-location: audio\iprefetchoffset.htm
old-project: audio
ms.assetid: 8c6a3766-c959-4979-8dc9-3b5234003272
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPreFetchOffset
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IPreFetchOffset interface



## -description
The <code>IPreFetchOffset</code> interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream. A WavePci miniport driver can use this interface to prevent the prefetch offset from growing too large when the driver allocates a large number of mappings. This interface is supported only in Windows XP and later. To determine whether the WavePci port driver supports the <code>IPreFetchOffset</code> interface, a miniport driver calls the port stream (<a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IPreFetchOffset</b>. 

For more information about the <code>IPreFetchOffset</code> interface, see <a href="https://msdn.microsoft.com/92a0163f-29b1-4e15-88ab-67e1097d015e">Prefetch Offsets</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPreFetchOffset</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPreFetchOffset</b> also has these types of members:

The <b>IPreFetchOffset</b> interface has these methods.

The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.

 


## -members
The <b>IPreFetchOffset</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iprefetchoffset_setprefetchoffset">IPreFetchOffset::SetPreFetchOffset</a>
</td>
<td align="left" width="63%">
The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.

</td>
</tr>
</table>The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>