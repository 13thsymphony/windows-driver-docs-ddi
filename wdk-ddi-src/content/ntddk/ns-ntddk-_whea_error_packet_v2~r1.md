---
UID: NS.NTDDK._WHEA_ERROR_PACKET_V2~R1
title: _WHEA_ERROR_PACKET_V2
author: windows-driver-content
description: The WHEA_ERROR_PACKET_V2 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V2 structure is supported in Windows 7 and later versions of Windows.
old-location: whea\whea_error_packet_v2.htm
old-project: whea
ms.assetid: 10cfc201-d5c9-4887-997e-673ef6abb7db
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_ERROR_PACKET_V2, WHEA_ERROR_PACKET_V2, *PWHEA_ERROR_PACKET, WHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_PACKET_V2
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _WHEA_ERROR_PACKET_V2 structure



## -description
The WHEA_ERROR_PACKET_V2 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).



## -syntax

````
typedef struct _WHEA_ERROR_PACKET_V2 {
  ULONG                         Signature;
  ULONG                         Version;
  ULONG                         Length;
  WHEA_ERROR_PACKET_FLAGS       Flags;
  WHEA_ERROR_TYPE               ErrorType;
  WHEA_ERROR_SEVERITY           ErrorSeverity;
  ULONG                         ErrorSourceId;
  WHEA_ERROR_SOURCE_TYPE        ErrorSourceType;
  GUID                          NotifyType;
  ULONGLONG                     Context;
  WHEA_ERROR_PACKET_DATA_FORMAT DataFormat;
  ULONG                         Reserved1;
  ULONG                         DataOffset;
  ULONG                         DataLength;
  ULONG                         PshedDataOffset;
  ULONG                         PshedDataLength;
} WHEA_ERROR_PACKET_V2, *PWHEA_ERROR_PACKET_V2;
````


## -struct-fields

### -field Signature

The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V2_SIGNATURE.


### -field Version

The version of the WHEA_ERROR_PACKET_V2 structure. This member contains the value WHEA_ERROR_PKT_V2_VERSION.


### -field Length

The size, in bytes, of the hardware error packet, including the hardware error data and PSHED data.


### -field Flags

A <a href="whea.whea_error_packet_flags">WHEA_ERROR_PACKET_FLAGS</a> union that specifies the format of the hardware error data. 


### -field ErrorType

A <a href="whea.whea_error_type">WHEA_ERROR_TYPE</a> value that specifies the type of hardware component that reported the hardware error.


### -field ErrorSeverity

A <a href="whea.whea_error_severity">WHEA_ERROR_SEVERITY</a> value that specifies the severity of the error condition.


### -field ErrorSourceId

The identifier of the error source that reported the hardware error.


### -field ErrorSourceType

A <a href="whea.whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a> value that indicates the type of the error source that reported the hardware error.


### -field NotifyType

A GUID that identifies the notification mechanism by which an error condition is reported to the operating system. The following are the GUIDs for the standard notification types:




### -field CMC_NOTIFY_TYPE_GUID

Corrected Machine Check (CMC)


### -field CPE_NOTIFY_TYPE_GUID

Corrected Platform Error (CPE)


### -field MCE_NOTIFY_TYPE_GUID

Machine Check Exception (MCE)


### -field PCIe_NOTIFY_TYPE_GUID

PCI Express (PCIe) Error


### -field INIT_NOTIFY_TYPE_GUID

INIT Error Record (INIT)


### -field NMI_NOTIFY_TYPE_GUID

Nonmaskable Interrupt (NMI)


### -field BOOT_NOTIFY_TYPE_GUID

Boot Error Record (BOOT)

</dd>
</dl>
For error notification types that do not conform to one of the standard types in the previous list, a platform-specific GUID can be defined to identify the notification mechanism. If the notification type does not correspond to any of the standard notification types or any platform-specific notification types, this member is set to GENERIC_NOTIFY_TYPE_GUID.


### -field Context

Reserved for system use.


### -field DataFormat

A <a href="whea.whea_error_packet_data_format">WHEA_ERROR_PACKET_DATA_FORMAT</a> value  that indicates the format of the hardware error information that is contained in the data that is referenced through the <b>DataOffset </b>and <b>DataLength</b> members.


### -field Reserved1

Reserved for system use.


### -field DataOffset

An offset, in bytes, for hardware error data from the status registers for the error source. The format of the hardware error data is specified by the <b>DataFormat</b> member. The offset of the hardware error information is relative to the start of the WHEA_ERROR_PACKET_V2 structure.


### -field DataLength

The length, in bytes, of the hardware error data.


### -field PshedDataOffset

An offset, in bytes, for a data buffer where a PSHED plug-in can add additional platform-specific error data to the hardware error packet. The offset of the PSHED data buffer is relative to the start of the WHEA_ERROR_PACKET_V2 structure.


### -field PshedDataLength

The length, in bytes, of the PSHED data buffer.


## -remarks
The WHEA_ERROR_PACKET_V2 structure is used to report a hardware error in Windows 7 and later versions of Windows. If your <a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">platform-specific hardware error driver (PSHED) plug-ins</a> run on any WHEA-compatible Windows version, You can inspect the version of WHEA_ERROR_PACKET by following these steps:

If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V1, the code is running on an early version of Windows, and the error packet is formatted as a <a href="whea.whea_error_packet_v1">WHEA_ERROR_PACKET_V1</a> structure.

If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2, the code is running on a later version of Windows, and the error packet is formatted as a <b>WHEA_ERROR_PACKET_V2</b> structure.

An LLHEH passes a WHEA_ERROR_PACKET_V2 structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error status registers for the error source.

The WHEA_ERROR_PACKET_V2 structure describes the error data that is contained in a hardware error packet error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. The hardware error data is referenced through the <b>DataOffset </b>and<b> DataLength </b>members. The error data's type is defined through the <b>DataFormat</b> member.

In addition, <a href="whea.platform_specific_hardware_error_driver_plug_ins">platform-specific hardware error driver (PSHED) plug-ins</a> can add supplementary platform-specific error data that is referenced through the <b>PshedDataOffset</b> and <b>PshedDataLength</b> members. Both of these members must be set to 0 if PSHED data has not been added.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 7 and later versions of Windows.


</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">Platform-Specific Hardware Error Driver (PSHED) Plug-Ins</a>
</dt>
<dt>
<a href="whea.whea_error_packet_data_format">WHEA_ERROR_PACKET_DATA_FORMAT</a>
</dt>
<dt>
<a href="whea.whea_error_packet_flags">WHEA_ERROR_PACKET_FLAGS</a>
</dt>
<dt>
<a href="whea.whea_error_packet_v1">WHEA_ERROR_PACKET_V1</a>
</dt>
<dt>
<a href="whea.whea_error_severity">WHEA_ERROR_SEVERITY</a>
</dt>
<dt>
<a href="whea.whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a>
</dt>
<dt>
<a href="whea.whea_error_type">WHEA_ERROR_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_V2 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

