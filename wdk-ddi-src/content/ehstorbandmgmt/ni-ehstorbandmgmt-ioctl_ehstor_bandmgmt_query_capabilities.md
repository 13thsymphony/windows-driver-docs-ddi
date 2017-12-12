---
UID: NI.ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
title: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
author: windows-driver-content
description: The IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a BAND_MANAGEMENT_CAPABILITIES structure in the system buffer.
old-location: storage\ioctl_ehstor_bandmgmt_query_capabilities.htm
old-project: storage
ms.assetid: 16D035EF-2234-4D5A-8D19-8CF3BA8B3590
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_VideoSample32, DXVA_VideoSample32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
req.alt-loc: EhStorBandMgmt.h
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

# IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES IOCTL



## -description
The <b>IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</b> request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a <a href="storage.band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a> structure in the system buffer.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="storage.band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>  structure.


### -output-buffer-length
The length of a <a href="storage.band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>  structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field contains the number of bytes returned in the output buffer. One of the following values can be returned in the <b>Status</b> field. 

 


## -remarks
A driver or application can query for the necessary output buffer size by setting the output buffer for the request to NULL and the output size to 0. The <b>IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</b> request will return with the <b>Status</b> field of the <i>IoStatus</i> block set to STATUS_BUFFER_OVERFLOW and the <b>Information</b> field will contain the required buffer size.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>EhStorBandMgmt.h (include EhStorBandMgmt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

