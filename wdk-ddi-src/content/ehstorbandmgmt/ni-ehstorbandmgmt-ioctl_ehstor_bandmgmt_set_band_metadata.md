---
UID: NI.ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
author: windows-driver-content
description: Metadata associated with a band is set with an IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_metadata.htm
old-project: storage
ms.assetid: 5FBEAB29-C256-47EF-B673-6584679B8908
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_VideoSample32, DXVA_VideoSample32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
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

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA IOCTL



## -description
Metadata associated with a band is set with an <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</b> request. The metadata for a band serves as a data area for a key manager application.



## -ioctlparameters

### -input-buffer
The input buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a <a href="storage.set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a> and possibly an <b>AUTH_KEY</b> structure along with the new metadata to set for the band. 

If the <b>AuthKeyOffset</b> member of <a href="storage.set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_METADATA_PARAMETERS)    + <b>MetadataSize</b> + <b>sizeof</b>(AUTH_KEY).


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values may be returned in the <b>Status</b> field: 

 


## -remarks
Metadata can also be erased by using this IOCTL. To erase metadata for a band, set the metadata portion of input buffer to all zeros or some other erase pattern. To ensure removal of sensitive information in metadata blobs, this erase operation should be performed prior to deleting a band from the silo driver's band table.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 8 and later versions of Windows.

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
<a href="storage.set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

