---
UID : NS:pepfx._PEP_QUERY_SOC_SUBSYSTEM_METADATA
title : "_PEP_QUERY_SOC_SUBSYSTEM_METADATA"
author : windows-driver-content
description : The PEP_QUERY_SOC_SUBSYSTEM_METADATA structure is used with the PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried.
old-location : kernel\pep_query_soc_subsystem_metadata.htm
old-project : kernel
ms.assetid : D823EF66-1440-45B7-A0D8-A98522AA69E1
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : pepfx/PPEP_QUERY_SOC_SUBSYSTEM_METADATA, PEP_QUERY_SOC_SUBSYSTEM_METADATA, PEP_QUERY_SOC_SUBSYSTEM_METADATA structure [Kernel-Mode Driver Architecture], pepfx/PEP_QUERY_SOC_SUBSYSTEM_METADATA, PPEP_QUERY_SOC_SUBSYSTEM_METADATA structure pointer [Kernel-Mode Driver Architecture], PPEP_QUERY_SOC_SUBSYSTEM_METADATA, kernel.pep_query_soc_subsystem_metadata, _PEP_QUERY_SOC_SUBSYSTEM_METADATA, *PPEP_QUERY_SOC_SUBSYSTEM_METADATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_QUERY_SOC_SUBSYSTEM_METADATA, PEP_QUERY_SOC_SUBSYSTEM_METADATA"
---

# _PEP_QUERY_SOC_SUBSYSTEM_METADATA structure
The <b>PEP_QUERY_SOC_SUBSYSTEM_METADATA</b> structure is used with the <b>PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</b> notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried.

## Syntax
````
typedef struct _PEP_QUERY_SOC_SUBSYSTEM_METADATA {
  ULONG                       PlatformIdleStateIndex;
  PVOID                       SubsystemHandle;
  PCUNICODE_STRING            SubsystemName;
  ULONG                       Flags;
  ULONG                       MetadataCount;
  PPEP_SOC_SUBSYSTEM_METADATA Metadata[ANYSIZE_ARRAY];
} PEP_QUERY_SOC_SUBSYSTEM_METADATA, *PPEP_QUERY_SOC_SUBSYSTEM_METADATA;
````

## Members


`Flags`

This member is reserved and should be set to zero.

`Metadata`

[in/out] An array of pointers to <a href="..\pepfx\ns-pepfx-_pep_soc_subsystem_metadata.md">PEP_SOC_SUBSYSTEM_METADATA</a> structures.  Each entry holds one key/value metadata string-pair.

`MetadataCount`

[in] The number of entries in the <b>Metadata</b> array.  The PEP previously provided this value as <b>PEP_QUERY_SOC_SUBSYSTEM.MetadataCount</b>.

`PlatformIdleStateIndex`

[in] The platform idle state index for  for the SoC subsystem that the OS is querying.

`SubsystemHandle`

[in] A context pointer that the PEP previously provided on subsystem initialization. The context pointer is optional, so if none was provided then the value will be zero. The PEP is free to ignore this field.

`SubsystemName`

[in] The name of the subsystem whose metadata is being queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_soc_subsystem_metadata.md">PEP_SOC_SUBSYSTEM_METADATA</a>

<b>PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_SOC_SUBSYSTEM_METADATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>