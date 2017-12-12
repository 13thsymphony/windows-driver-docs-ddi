---
UID: NS.BTHIOCTL._BTH_SDP_RECORD
title: _BTH_SDP_RECORD
author: windows-driver-content
description: The BTH_SDP_RECORD structure contains information about an SDP record that is to be added to the local SDP server.
old-location: bltooth\bth_sdp_record.htm
old-project: bltooth
ms.assetid: 29aeb49a-1647-46ee-a88e-f088f8a2548f
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BTH_SDP_RECORD, *PBTH_SDP_RECORD, BTH_SDP_RECORD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTH_SDP_RECORD
req.alt-loc: bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
---

# _BTH_SDP_RECORD structure



## -description
The BTH_SDP_RECORD structure contains information about an SDP record that is to be added to the
  local SDP server.



## -syntax

````
typedef struct _BTH_SDP_RECORD {
  ULONG fSecurity;
  ULONG fOptions;
  ULONG fCodService;
  ULONG recordLength;
  UCHAR record[1];
} BTH_SDP_RECORD, *PBTH_SDP_RECORD;
````


## -struct-fields

### -field fSecurity

A combination of flags that specifies the security attributes of the SDP record. Valid flag values
     are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SERVICE_SECURITY_AUTHENTICATE

</td>
<td>
Only authenticated clients can access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_AUTHORIZE

</td>
<td>
Only authorized clients can access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_ENCRYPT_OPTIONAL

</td>
<td>
Encryption is optional to access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_ENCRYPT_REQUIRED

</td>
<td>
Encryption is required to access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_NONE

</td>
<td>
No security is required to access this record.

</td>
</tr>
</table>
 


### -field fOptions

A combination of flags that specifies the publication options for the SDP record. Valid flag
     values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SERVICE_OPTION_DO_NOT_PUBLISH

</td>
<td>
The record should be entered into the local SDP server, but should not be published to remote
        systems.

</td>
</tr>
<tr>
<td>
SERVICE_OPTION_NO_PUBLIC_BROWSE

</td>
<td>
The record should be obtainable if specifically requested, but it should not be browseable using
        SDP browse groups.

</td>
</tr>
</table>
 


### -field fCodService


### -field A combination of flags that specifies the class of device (CoD) that the SDP record supports.
     Multiple flags can be set for a single device. Possible values include:

### -field COD_SERVICE_AUDIO
     

### -field COD_SERVICE_CAPTURING
     

### -field COD_SERVICE_INFORMATION
     

### -field COD_SERVICE_LIMITED
     

### -field COD_SERVICE_NETWORKING
     

### -field COD_SERVICE_OBJECT_XFER
     

### -field COD_SERVICE_POSITIONING
     

### -field COD_SERVICE_RENDERING
     

### -field COD_SERVICE_TELEPHONY


### -field recordLength

The size, in bytes, of the record.


### -field record


      The SDP record in its raw stream format. The first byte is defined in this structure, with the
      entire record following it.
     


## -remarks
This structure is passed as the input buffer and output buffer of 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
    IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthioctl.h (include Bthioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
   IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_RECORD structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

