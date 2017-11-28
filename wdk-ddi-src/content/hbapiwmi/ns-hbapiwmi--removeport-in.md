---
UID: NS.hbapiwmi._RemovePort_IN
title: RemovePort_IN
author: windows-driver-content
description: The Remove_IN structure is used by a WMI client to deliver input parameter data to the RemovePort WMI method.
old-location: storage\removeport_in.htm
old-project: storage
ms.assetid: 2f32e44a-e4a6-4745-9749-fc611119cc0e
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: RemovePort_IN, RemovePort_IN, *PRemovePort_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemovePort_IN
req.alt-loc: hbapiwmi.h
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

# RemovePort_IN structure



## -description
<p>The Remove_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a> WMI method.</p>


## -syntax

````
typedef struct _RemovePort_IN {
  UCHAR PortWWN[8];
} RemovePort_IN, *PRemovePort_IN;
````


## -struct-fields
<dl>

### -field <b>PortWWN</b>

<dd>
<p>Contains a worldwide name that indicates the port that should be removed from the list of ports whose events are reported to the WMI client.. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the RemovePort_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePort_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
