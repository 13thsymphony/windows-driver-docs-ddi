---
UID: NS.EHSTORBANDMGMT._BAND_MANAGEMENT_CAPABILITIES
title: _BAND_MANAGEMENT_CAPABILITIES
author: windows-driver-content
description: The BAND_MANAGEMENT_CAPABILITIES structure contains the security capabilities available for a storage device. This structure is returned in the system buffer by the IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request.
old-location: storage\band_management_capabilities.htm
old-project: storage
ms.assetid: 102C7CEC-B1DD-49F6-AB7F-0CE0A22EBE54
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _BAND_MANAGEMENT_CAPABILITIES, PBAND_MANAGEMENT_CAPABILITIES, BAND_MANAGEMENT_CAPABILITIES, *PBAND_MANAGEMENT_CAPABILITIES
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
req.alt-api: BAND_MANAGEMENT_CAPABILITIES
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

# _BAND_MANAGEMENT_CAPABILITIES structure



## -description
The <b>BAND_MANAGEMENT_CAPABILITIES</b> structure contains the security capabilities available for a storage device. This structure is returned in the system buffer by the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> request.



## -syntax

````
typedef struct _BAND_MANAGEMENT_CAPABILITIES {
  ULONG     StructSize;
  ULONG     Capabilities;
  ULONGLONG KeyProtectionMechanism;
  ULONG     MinAuthKeyLength;
  ULONG     MaxAuthKeyLength;
  ULONG     MaxBandCount;
  ULONG     MaxSimultaneousReencryptionCount;
  ULONG     BandMetadataSize;
} BAND_MANAGEMENT_CAPABILITIES, *PBAND_MANAGEMENT_CAPABILITIES;
````


## -struct-fields

### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(BAND_MANAGEMENT_CAPABILITIES).


### -field Capabilities

Security capability flags for a storage device. This is a bitwise OR value of the following flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CAPS_ACTIVATED

</td>
<td width="60%">
If set, the capability members of this structure are available. Otherwise, the remaining members of this structure are not valid.

</td>
</tr>
<tr>

### -field CAPS_BANDCROSSING_SUPPORTED

</td>
<td width="60%">
The storage device supports reads and writes across multiple bands. If this flag is not set, single reads or writes  spanning multiple bands are divided into multiple IO requests for a device.

</td>
</tr>
<tr>

### -field CAPS_SID_SECURED

</td>
<td width="60%">
SID authority is secured. If set, the default SID pin cannot be used to modify the security configuration of the storage device.

</td>
</tr>
</table>
 


### -field KeyProtectionMechanism

The mechanism used to protect the media keys. This member is set to one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field 0

</td>
<td width="60%">
Keys are not protected.

</td>
</tr>
<tr>

### -field MEDIAKEY_PROTECTEDBY_VENDORSCHEME

</td>
<td width="60%">
Keys are protected by a vendor-supplied method. Do not use. This option is not supported.

</td>
</tr>
<tr>

### -field MEDIAKEY_PROTECTEDBY_AUTHKEY

</td>
<td width="60%">
Keys are encrypted by keys derived from band authentication keys. Key derivation results in negligible entropy loss from the band authentication data.

</td>
</tr>
</table>
 


### -field MinAuthKeyLength

The minimum length, in bytes, of the  band authentication or erase keys accepted by the storage device.


### -field MaxAuthKeyLength

The maximum length, in bytes, of the  band authentication or erase keys accepted by the storage device.


### -field MaxBandCount

The maximum number of simultaneous bands configured in the storage device. This includes the global band.


### -field MaxSimultaneousReencryptionCount

The number of simultaneous band re-encryptions the hardware on the device supports. If this member is 0, hardware-driven band re-encryptions are not supported.


### -field BandMetadataSize

The size, in bytes, of the per band metadata store.


## -remarks
If <b>CAPS_ACTIVATED</b> is not set in <b>Capabilities</b>, security functionality can be activated with the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a> request.


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
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_MANAGEMENT_CAPABILITIES structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

