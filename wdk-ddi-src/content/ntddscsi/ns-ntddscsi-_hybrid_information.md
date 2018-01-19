---
UID : NS:ntddscsi._HYBRID_INFORMATION
title : _HYBRID_INFORMATION
author : windows-driver-content
description : The HYBRID_INFORMATION structure contains hybrid disk capability information.
old-location : storage\hybrid_information.htm
old-project : storage
ms.assetid : 5CD8E422-8CEE-43E8-9703-520FDBE6BF5E
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _HYBRID_INFORMATION, *PHYBRID_INFORMATION, HYBRID_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddscsi.h
req.include-header : Ntddscsi.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.1.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HYBRID_INFORMATION
req.alt-loc : Ntddscsi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PHYBRID_INFORMATION, HYBRID_INFORMATION"
---

# _HYBRID_INFORMATION structure
The <b>HYBRID_INFORMATION</b> structure contains hybrid disk capability information. The structure is returned when the HYBRID_FUNCTION_GET_INFO function is selected in a <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_hybrid.md">IOCTL_SCSI_MINIPORT_HYBRID</a> request  sent to an HBA miniport driver.

## Syntax
````
typedef struct _HYBRID_INFORMATION {
  ULONG          Version;
  ULONG          Size;
  BOOLEAN        HybridSupported;
  NVCACHE_STATUS Status;
  NVCACHE_TYPE   CacheTypeEffective;
  NVCACHE_TYPE   CacheTypeDefault;
  ULONG          FractionBase;
  ULONGLONG      CacheSize;
  struct {
    ULONG WriteCacheChangeable  :1;
    ULONG WriteThroughIoSupported  :1;
    ULONG FlushCacheSupported  :1;
    ULONG Removable  :1;
    ULONG ReservedBits  :28;
  } Attributes;
  struct {
    UCHAR                             PriorityLevelCount;
    BOOLEAN                           MaxPriorityBehavior;
    ULONG                             DirtyThresholdLow;
    ULONG                             DirtyThresholdHigh;
    struct {
      ULONG CacheDisable  :1;
      ULONG SetDirtyThreshold  :1;
      ULONG PriorityDemoteBySize  :1;
      ULONG PriorityChangeByLbaRange  :1;
      ULONG Evict  :1;
      ULONG ReservedBits  :27;
      ULONG MaxEvictCommands;
      ULONG MaxLbaRangeCountForEvict;
      ULONG MaxLbaRangeCountForChangeLba;
    } SupportedCommands;
    NVCACHE_PRIORITY_LEVEL_DESCRIPTOR Priority[];
  } Priorities;
} HYBRID_INFORMATION, *PHYBRID_INFORMATION;
````

## Members

        
            `Attributes`

            The hybrid disk attributes.
        
            `CacheSize`

            The size, in LBAs, of the non-volatile on the hybrid disk.
        
            `CacheTypeDefault`

            The default caching type used by the hybrid disk. The possible values are the same as for <b>CacheTypeEffective</b>.
        
            `CacheTypeEffective`

            The non-volatile caching type currently set for hybrid disk. The effective cache type is one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `FractionBase`

            The base value for fractional fields in this structure. This value is set to 255.
        
            `HybridSupported`

            Miniport supports for hybrid disks. Set to <b>TRUE</b> if hybrid disks are supported. Otherwise, <b>FALSE</b>.
        
            `Priorities`

            Priority settings for the hybrid disk.
        
            `Size`

            The size of this structure. Set to <b>sizeof</b>(HYBRID_INFORMATION).
        
            `Status`

            The status of the hybrid disk cache. This contains one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `Version`

            The version of this structure. Set to HYBRID_REQUEST_INFO_STRUCTURE_VERSION.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_hybrid.md">IOCTL_SCSI_MINIPORT_HYBRID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HYBRID_INFORMATION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>