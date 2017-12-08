---
UID: NS.ehstorbandmgmt._SET_BAND_METADATA_PARAMETERS
title: SET_BAND_METADATA_PARAMETERS
author: windows-driver-content
description: The metadata for a configured band is set to the parameters in a SET_BAND_METADATA_PARAMETERS structure. This structure is input for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request.
old-location: storage\set_band_metadata_parameters.htm
old-project: storage
ms.assetid: 3FCCFFE1-C341-4C8D-8EEC-E07C7ECFC317
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SET_BAND_METADATA_PARAMETERS, SET_BAND_METADATA_PARAMETERS, *PSET_BAND_METADATA_PARAMETERS
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
req.alt-api: SET_BAND_METADATA_PARAMETERS
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

# SET_BAND_METADATA_PARAMETERS structure



## -description
<p>The metadata for a configured band is set to the parameters in a <b>SET_BAND_METADATA_PARAMETERS</b> structure. This structure is input for a <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-set-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> request.</p>


## -syntax

````
typedef struct _SET_BAND_METADATA_PARAMETERS {
  ULONG         StructSize;
  ULONG         BandId;
  LARGE_INTEGER BandStart;
  ULONG         MetadataOffset;
                MetadataSize;
  ULONG         BufferOffset;
  ULONG         AuthKeyOffset;
} SET_BAND_METADATA_PARAMETERS, *PSET_BAND_METADATA_PARAMETERS;
````


## -struct-fields
<dl>

### -field StructSize

<dd>
<p>The size of this structure in bytes. Set to <b>sizeof</b>(SET_BAND_METADATA_PARAMETERS).</p>
</dd>

### -field BandId

<dd>
<p>The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.</p>
</dd>

### -field BandStart

<dd>
<p>The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.</p>
</dd>

### -field MetadataOffset

<dd>
<p>The offset from the start of the band metadata property  to set the new   data.</p>
</dd>

### -field MetadataSize

<dd>
<p>The length of metadata bytes to set. This size is limited by the value of <b>MetadataOffset</b> subtracted from the <b>BandMetadataSize</b> member of the <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt--band-management-capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a> structure.</p>
</dd>

### -field BufferOffset

<dd>
<p>The offset, in bytes, from the beginning of <b>SET_BAND_METADATA_PARAMETERS </b> to the location of the new metadata.</p>
</dd>

### -field AuthKeyOffset

<dd>
<p>The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the authorization key for the band. The offset is from the beginning of <b>SET_BAND_METADATA_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AUTH_KEY
{
    ULONG   KeySize;
    UCHAR   Key[ANYSIZE_ARRAY];
} AUTH_KEY;</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field KeySize

<dd>
<p>Size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.</p>
</dd>

### -field Key

<dd>
<p>A variable-length byte array that contains the key data.</p>
</dd>
</dl>
<p>To specify a default authentication key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.</p>
</dd>
</dl>

## -remarks
<p> Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt--band-management-capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == -1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-set-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a>.</p>

<p>If <b>BandID</b> and <b>BandStart</b> are both set to –1,  then the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-set-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> sets metadata for the global band.</p>

<p>The size of the  band metadata store is found in the <b>BandMetadataSize</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt--band-management-capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>. This structure is returned from a <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-query-capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> request.</p>

<p>The new metadata to set for the band is included in the system buffer for  the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-set-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> request and follows this structure at <b>BufferOffset</b>.</p>

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
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-query-capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl-ehstor-bandmgmt-set-band-metadata.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SET_BAND_METADATA_PARAMETERS structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
