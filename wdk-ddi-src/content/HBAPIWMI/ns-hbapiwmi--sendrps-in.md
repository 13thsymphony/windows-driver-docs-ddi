---
UID: NS.hbapiwmi._SendRPS_IN
title: SendRPS_IN
author: windows-driver-content
description: The SendRPS_IN structure is used to deliver input parameter data to the SendRPS WMI method.
old-location: storage\sendrps_in.htm
ms.assetid: 7ab8986d-1e28-4d25-888f-cd10e310d623
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SendRPS_IN
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
ms.keywords: SendRPS_IN, SendRPS_IN, *PSendRPS_IN
req.iface: 
---

# SendRPS_IN structure



## -description
<p>The SendRPS_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a> WMI method.</p>


## -syntax

````
typedef struct _SendRPS_IN {
  UCHAR PortWWN[8];
  UCHAR AgentWWN[8];
  UCHAR ObjectWWN[8];
  ULONG AgentDomain;
  ULONG ObjectPortNumber;
} SendRPS_IN, *PSendRPS_IN;
````


## -struct-fields
<dl>

### -field <b>PortWWN</b>

<dd>
<p>Contains a worldwide name for the local port through which the RPS command is sent. </p>
</dd>

### -field <b>AgentWWN</b>

<dd>
<p>Contains a worldwide name for the port that is to be queried for the status of the port indicated by <b>ObjectWWN</b>. </p>
</dd>

### -field <b>ObjectWWN</b>

<dd>
<p>Contains the worldwide name of the port for which port status is to be returned. </p>
</dd>

### -field <b>AgentDomain</b>

<dd>
<p>Contains the domain number of the domain controller to be queried for the status of the port indicated by <b>ObjectWWN</b>. </p>
</dd>

### -field <b>ObjectPortNumber</b>

<dd>
<p>Contains the worldwide name of the port for which port status is to be returned. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SendRPS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SendRPS_IN structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
