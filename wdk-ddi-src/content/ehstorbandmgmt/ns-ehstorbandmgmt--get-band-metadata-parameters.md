---
UID: NS.ehstorbandmgmt._GET_BAND_METADATA_PARAMETERS
title: GET_BAND_METADATA_PARAMETERS
author: windows-driver-content
description: The metadata for a configured band is retrieved according to the parameters in a GET_BAND_METADATA_PARAMETERS structure. This structure is input for an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request.
old-location: storage\get_band_metadata_parameters.htm
old-project: storage
ms.assetid: CE8160C5-8C64-4BA5-864E-EC634754E062
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: GET_BAND_METADATA_PARAMETERS, GET_BAND_METADATA_PARAMETERS, *PGET_BAND_METADATA_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GET_BAND_METADATA_PARAMETERS
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
req.iface: 
---

# GET_BAND_METADATA_PARAMETERS structure



## -description
<p>The metadata for a configured band is retrieved according to the parameters in a <b>GET_BAND_METADATA_PARAMETERS</b> structure. This structure is input for an <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-get-band-metadata.md"> IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> request.</p>


## -syntax

````
typedef struct _GET_BAND_METADATA_PARAMETERS {
  ULONG         StructSize;
  ULONG         BandId;
  LARGE_INTEGER BandStart;
  ULONG         MetadataOffset;
                MetadataSize;
} GET_BAND_METADATA_PARAMETERS, *PGET_BAND_METADATA_PARAMETERS;
````


## -struct-fields
<dl>

### -field <b>StructSize</b>

<dd>
<p>The size of this structure in bytes. Set to <b>sizeof</b>(GET_BAND_METADATA_PARAMETERS).</p>
</dd>

### -field <b>BandId</b>

<dd>
<p>The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.</p>
</dd>

### -field <b>BandStart</b>

<dd>
<p>The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.</p>
</dd>

### -field <b>MetadataOffset</b>

<dd>
<p>The offset from the start of the band metadata property  to retrieve  data from.</p>
</dd>

### -field <b>MetadataSize</b>

<dd>
<p>The length of metadata bytes to retrieve.</p>
</dd>
</dl>

## -remarks
<p> Precedence is given to <b>BandID</b> for band selection.  If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt--band-management-capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-get-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a>.</p>

<p>If <b>BandID</b> and <b>BandStart</b> are both set to –1,  then the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-get-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> returns metadata for the global band.</p>

<p>If <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-get-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> was successful, <i>Parameters.DeviceIoControl.InputBufferLength</i> equals the value in <b>MetadataSize</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt--band-management-capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-get-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GET_BAND_METADATA_PARAMETERS structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
