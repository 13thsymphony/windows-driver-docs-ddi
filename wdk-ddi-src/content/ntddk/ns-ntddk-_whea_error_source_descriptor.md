---
UID: NS:ntddk._WHEA_ERROR_SOURCE_DESCRIPTOR
title: _WHEA_ERROR_SOURCE_DESCRIPTOR
author: windows-driver-content
description: The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source.
old-location: whea\whea_error_source_descriptor.htm
old-project: whea
ms.assetid: 59ee6d51-c60a-4a71-b831-1b9437a69d34
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_ERROR_SOURCE_DESCRIPTOR, *PWHEA_ERROR_SOURCE_DESCRIPTOR, WHEA_ERROR_SOURCE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_SOURCE_DESCRIPTOR
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
req.typenames: *PWHEA_ERROR_SOURCE_DESCRIPTOR, WHEA_ERROR_SOURCE_DESCRIPTOR
---

# _WHEA_ERROR_SOURCE_DESCRIPTOR structure



## -description
The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source.



## -syntax

````
typedef struct _WHEA_ERROR_SOURCE_DESCRIPTOR {
  ULONG                   Length;
  ULONG                   Version;
  WHEA_ERROR_SOURCE_TYPE  Type;
  WHEA_ERROR_SOURCE_STATE State;
  ULONG                   MaxRawDataLength;
  ULONG                   NumRecordsToPreallocate;
  ULONG                   MaxSectionsPerRecord;
  ULONG                   ErrorSourceId;
  ULONG                   PlatformErrorSourceId;
  ULONG                   Flags;
  union {
    WHEA_XPF_MCE_DESCRIPTOR       XpfMceDescriptor;
    WHEA_XPF_CMC_DESCRIPTOR       XpfCmcDescriptor;
    WHEA_XPF_NMI_DESCRIPTOR       XpfNmiDescriptor;
    WHEA_IPF_MCA_DESCRIPTOR       IpfMcaDescriptor;
    WHEA_IPF_CMC_DESCRIPTOR       IpfCmcDescriptor;
    WHEA_IPF_CPE_DESCRIPTOR       IpfCpeDescriptor;
    WHEA_AER_ROOTPORT_DESCRIPTOR  AerRootportDescriptor;
    WHEA_AER_ENDPOINT_DESCRIPTOR  AerEndpointDescriptor;
    WHEA_AER_BRIDGE_DESCRIPTOR    AerBridgeDescriptor;
    WHEA_GENERIC_ERROR_DESCRIPTOR GenErrDescriptor;
  } Info;
} WHEA_ERROR_SOURCE_DESCRIPTOR, *PWHEA_ERROR_SOURCE_DESCRIPTOR;
````


## -struct-fields

### -field Length

The size, in bytes, of the WHEA_ERROR_SOURCE_DESCRIPTOR structure.


### -field Version

The version number of the WHEA_ERROR_SOURCE_DESCRIPTOR structure. This member contains the value WHEA_ERROR_SOURCE_DESCRIPTOR_VERSION_10.


### -field Type

A <a href="..\ntddk\ne-ntddk-_whea_error_source_type.md">WHEA_ERROR_SOURCE_TYPE</a>-typed value that specifies the type of the error source.


### -field State

A <a href="..\ntddk\ne-ntddk-_whea_error_source_state.md">WHEA_ERROR_SOURCE_STATE</a>-typed value that specifies the state of the error source.


### -field MaxRawDataLength

The maximum number of bytes of raw data included in a hardware error packet that is reported by this error source. This number must be large enough to include any additional platform-specific error information that is added to the hardware error packet by the PSHED or by a PSHED plug-in.


### -field NumRecordsToPreallocate

The number of error records that should be pre-allocated for hardware errors that are reported by this error source.


### -field MaxSectionsPerRecord

The maximum number of error record sections that are required in an error record to describe a hardware error that is reported by this error source. This number must be large enough to include any additional error record sections that are added to the error record by the PSHED or by a PSHED plug-in during the processing of the error.


### -field ErrorSourceId

The identifier of the error source. This identifier is unique only on the system where the error source exists.


### -field PlatformErrorSourceId

The identifier of the error source as enumerated by the hardware platform. This identifier is unique only on the system where the error source exists.


### -field Flags

A bitwise OR'ed combination of flags that describes the error source. Possible flags are:




### -field WHEA_ERROR_SOURCE_FLAG_DEFAULTSOURCE

This flag indicates that the error source is a default error source for the type of hardware platform on which it exists.


### -field WHEA_ERROR_SOURCE_FLAG_FIRMWAREFIRST

This flag indicates that the errors that are reported by this error source are handled by the firmware before control of the hardware error processing is passed to the operating system.


### -field WHEA_ERROR_SOURCE_FLAG_GLOBAL

This flag indicates that the settings specified for the error source are to be applied to all of the error sources in the system that are of the same type as that specified in the <b>Type</b> member.

</dd>
</dl>

### -field Info

A union of descriptor structures that are specific to each different type of error source.


### -field XpfMceDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_xpf_mce_descriptor.md">WHEA_XPF_MCE_DESCRIPTOR</a> structure that describes an x86 or x64 processor machine check exception (MCE) error source.


### -field XpfCmcDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a> structure that describes an x86 or x64 processor corrected machine check (CMC) error source.


### -field XpfNmiDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_xpf_nmi_descriptor.md">WHEA_XPF_NMI_DESCRIPTOR</a> structure that describes an x86 or x64 processor nonmaskable interrupt (NMI) error source.


### -field IpfMcaDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_ipf_mca_descriptor.md">WHEA_IPF_MCA_DESCRIPTOR</a> structure that describes an Itanium processor machine check abort (MCA) error source.


### -field IpfCmcDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_ipf_cmc_descriptor.md">WHEA_IPF_CMC_DESCRIPTOR</a> structure that describes an Itanium processor corrected machine check (CMC) error source.


### -field IpfCpeDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_ipf_cpe_descriptor.md">WHEA_IPF_CPE_DESCRIPTOR</a> structure that describes an Itanium processor corrected platform error (CPE) error source.


### -field AerRootportDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_aer_rootport_descriptor.md">WHEA_AER_ROOTPORT_DESCRIPTOR</a> structure that describes a PCI Express (PCIe) root port error source.


### -field AerEndpointDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_aer_endpoint_descriptor.md">WHEA_AER_ENDPOINT_DESCRIPTOR</a> structure that describes a PCIe endpoint error source. 


### -field AerBridgeDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_aer_bridge_descriptor.md">WHEA_AER_BRIDGE_DESCRIPTOR</a> structure that describes a PCIe bridge error source.


### -field GenErrDescriptor

A <a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a> structure that describes a generic error source.

</dd>
</dl>

## -remarks
The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source. The WHEA_ERROR_SOURCE_DESCRIPTOR structure is also used to configure an error source.

A user-mode WHEA management application can control the error sources in the system by calling the methods in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559521">WHEAErrorSourceMethods</a> WMI provider class.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md">DisableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_enable_error_source.md">EnableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_all_error_sources.md">GetAllErrorSources</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_get_error_source_info.md">GetErrorSourceInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md">SetErrorSourceInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559523">WHEAErrorSourceMethods::DisableErrorSourceRtn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559525">WHEAErrorSourceMethods::EnableErrorSourceRtn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559527">WHEAErrorSourceMethods::GetAllErrorSourcesRtn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559530">WHEAErrorSourceMethods::GetErrorSourceInfoRtn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559531">WHEAErrorSourceMethods::SetErrorSourceInfoRtn</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_aer_bridge_descriptor.md">WHEA_AER_BRIDGE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_aer_endpoint_descriptor.md">WHEA_AER_ENDPOINT_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_aer_rootport_descriptor.md">WHEA_AER_ROOTPORT_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_whea_error_source_state.md">WHEA_ERROR_SOURCE_STATE</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_whea_error_source_type.md">WHEA_ERROR_SOURCE_TYPE</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_ipf_cmc_descriptor.md">WHEA_IPF_CMC_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_ipf_cpe_descriptor.md">WHEA_IPF_CPE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_ipf_mca_descriptor.md">WHEA_IPF_MCA_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_mce_descriptor.md">WHEA_XPF_MCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_nmi_descriptor.md">WHEA_XPF_NMI_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_SOURCE_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

