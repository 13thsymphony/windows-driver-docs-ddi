---
UID: NS.hbapiwmi._GetFC3MgmtInfo_OUT
title: GetFC3MgmtInfo_OUT
author: windows-driver-content
description: The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the GetFC3MgmtInfo WMI method to the WMI client.
old-location: storage\getfc3mgmtinfo_out.htm
old-project: storage
ms.assetid: 5cce25e7-582b-49b3-9f10-be59471e377f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: GetFC3MgmtInfo_OUT, GetFC3MgmtInfo_OUT, *PGetFC3MgmtInfo_OUT
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
req.alt-api: GetFC3MgmtInfo_OUT
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

# GetFC3MgmtInfo_OUT structure



## -description
<p>The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the <a href="storage.getfc3mgmtinfo">GetFC3MgmtInfo</a> WMI method to the WMI client.</p>


## -syntax

````
typedef struct _GetFC3MgmtInfo_OUT {
  ULONG          HBAStatus;
  HBAFC3MgmtInfo MgmtInfo;
} GetFC3MgmtInfo_OUT, *PGetFC3MgmtInfo_OUT;
````


## -struct-fields
<dl>

### -field <b>HBAStatus</b>

<dd>
<p>Contains a value associated with the WMI class qualifier <a href="storage.hba_status">HBA_STATUS</a> that indicates the result of an HBA query operation. </p>
</dd>

### -field <b>MgmtInfo</b>

<dd>
<p>Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi--hbafc3mgmtinfo.md">HBAFC3MgmtInfo</a> that reports FC3 management information. </p>
</dd>
</dl>

## -remarks
<p>The <a href="storage.getfc3mgmtinfo">GetFC3MgmtInfo</a> method reports fibre channel-3 management information.</p>

<p>The WMI tool suite generates a declaration of the GetEventBuffer_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.</p>

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
<a href="storage.getfc3mgmtinfo">GetFC3MgmtInfo</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
<dt>
<a href="..\hbapiwmi\ns-hbapiwmi--hbafc3mgmtinfo.md">HBAFC3MgmtInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFC3MgmtInfo_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
