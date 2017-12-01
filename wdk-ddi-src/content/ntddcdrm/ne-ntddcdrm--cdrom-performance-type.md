---
UID: NE.ntddcdrm._CDROM_PERFORMANCE_TYPE
title: CDROM_PERFORMANCE_TYPE
author: windows-driver-content
description: The CDROM_PERFORMANCE_TYPE enumeration defines the read and write performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location: storage\cdrom_performance_type.htm
old-project: storage
ms.assetid: 1039D4CB-11BA-4131-8CCE-7DCEE4B849D3
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: OUTPUT_PACKET, OUTPUT_PACKET, *POUTPUT_PACKET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_PERFORMANCE_TYPE
req.alt-loc: Ntddcdrm.h
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

# CDROM_PERFORMANCE_TYPE enumeration



## -description
<p>The <b>CDROM_PERFORMANCE_TYPE</b> enumeration defines the read and write performance data requests. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm--cdrom-performance-request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-get-performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request. </p>


## -syntax

````
typedef enum _CDROM_PERFORMANCE_TYPE { 
  CdromReadPerformance     = 1,
    CdromWritePerformance  = 2
} CDROM_PERFORMANCE_TYPE, *PCDROM_PERFORMANCE_TYPE;
````


## -enum-fields
<dl>

### -field <a id="CdromReadPerformance"></a><a id="cdromreadperformance"></a><a id="CDROMREADPERFORMANCE"></a><b>CdromReadPerformance</b>

<dd>
<p>Requests streaming read performance data.</p>
</dd>

### -field <a id="__CdromWritePerformance"></a><a id="__cdromwriteperformance"></a><a id="__CDROMWRITEPERFORMANCE"></a><b>  CdromWritePerformance</b>

<dd>
<p>Requests streaming write performance data.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--cdrom-performance-request.md">CDROM_PERFORMANCE_REQUEST</a>
</dt>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-get-performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_TYPE enumeration%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
