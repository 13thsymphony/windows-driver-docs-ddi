---
UID: NS.avc._AVC_MULTIFUNC_IRB
title: AVC_MULTIFUNC_IRB
author: windows-driver-content
description: The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.
old-location: stream\avc_multifunc_irb.htm
old-project: stream
ms.assetid: cd8090b1-47d7-4d82-86b3-757b0642c5fe
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: AVC_MULTIFUNC_IRB, AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_MULTIFUNC_IRB
req.alt-loc: avc.h
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
req.iface: 
---

# AVC_MULTIFUNC_IRB structure



## -description
<p>The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.</p>


## -syntax

````
typedef struct _AVC_MULTIFUNC_IRB {
  AVC_IRB Common;
  union {
    AVC_PIN_COUNT          PinCount;
    AVC_PIN_DESCRIPTOR     PinDescriptor;
    AVC_PRECONNECT_INFO    PreConnectInfo;
    AVC_SETCONNECT_INFO    SetConnectInfo;
    AVC_PIN_ID             PinId;
    AVC_EXT_PLUG_COUNTS    ExtPlugCounts;
    AVC_UNIQUE_ID          UniqueID;
    AVC_PEER_DO_LOCATOR    PeerLocator;
    AVC_PEER_DO_LIST       PeerList;
    AVC_SUBUNIT_INFO_BLOCK Subunits;
  };
} AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB;
````


## -struct-fields
<dl>

### -field <b>Common</b>

<dd>
<p> I/O Request Block (IRB) header structure where a function number is stored.</p>
</dd>

### -field <b>PinCount</b>

<dd>
<p>Used with AVC_FUNCTION_GET_PIN_COUNT.</p>
</dd>

### -field <b>PinDescriptor</b>

<dd>
<p>Used with AVC_FUNCTION_GET_PIN_DESCRIPTOR.</p>
</dd>

### -field <b>PreConnectInfo</b>

<dd>
<p>Used with AVC_FUNCTION_GET_CONNECT_INFO.</p>
</dd>

### -field <b>SetConnectInfo</b>

<dd>
<p>Used with AVC_FUNCTION_SET_CONNECT_INFO.</p>
</dd>

### -field <b>PinId</b>

<dd>
<p>Used with AVC_FUNCTION_ACQUIRE, <b>AVC_FUNCTION_RELEASE</b> and AVC_FUNCTION_CLR_CONNECTINFO.</p>
</dd>

### -field <b>ExtPlugCounts</b>

<dd>
<p>Used with AVC_FUNCTION_GET_EXT_PLUG_COUNTS.</p>
</dd>

### -field <b>UniqueID</b>

<dd>
<p>Used with AVC_FUNCTION_GET_UNIQUE_ID.</p>
</dd>

### -field <b>PeerLocator</b>

<dd>
<p>Used with AVC_FUNCTION_PEER_DO_LOCATOR.</p>
</dd>

### -field <b>PeerList</b>

<dd>
<p>Used with AVC_FUNCTION_PEER_DO_LIST.</p>
</dd>

### -field <b>Subunits</b>

<dd>
<p>Used with AVC_FUNCTION_GET_SUBUNIT_INFO.</p>
</dd>
</dl>

## -remarks
<p>The AVC_MULTIFUNC_IRB structure used with a variety of AV/C functionality. Depending on the functionality described in the AVC_IRB header, the matching, respective structure in the union is used.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554183">AVC_PIN_COUNT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554185">AVC_PIN_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554190">AVC_PRECONNECT_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554192">AVC_SETCONNECT_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554187">AVC_PIN_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554143">AVC_EXT_PLUG_COUNTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554200">AVC_UNIQUE_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554180">AVC_PEER_DO_LOCATOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554179">AVC_PEER_DO_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554199">AVC_SUBUNIT_INFO_BLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554158">AVC_FUNCTION_GET_PIN_COUNT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554160">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554166">AVC_FUNCTION_GET_UNIQUE_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554164">AVC_FUNCTION_GET_SUBUNIT_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_MULTIFUNC_IRB structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
