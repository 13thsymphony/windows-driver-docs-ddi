---
UID: NS:ntddscsi._HYBRID_INFORMATION
title: "_HYBRID_INFORMATION"
author: windows-driver-content
description: The HYBRID_INFORMATION structure contains hybrid disk capability information.
old-location: storage\hybrid_information.htm
old-project: storage
ms.assetid: 5CD8E422-8CEE-43E8-9703-520FDBE6BF5E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHYBRID_INFORMATION, HYBRID_INFORMATION, HYBRID_INFORMATION structure [Storage Devices], NvCacheNone, NvCacheStatusDisabled, NvCacheStatusDisabling, NvCacheStatusEnabled, NvCacheStatusUnknown, NvCacheTypeUnknown, NvCacheTypeWriteBack, NvCacheTypeWriteThrough, PHYBRID_INFORMATION, PHYBRID_INFORMATION structure pointer [Storage Devices], _HYBRID_INFORMATION, ntddscsi/HYBRID_INFORMATION, ntddscsi/PHYBRID_INFORMATION, storage.hybrid_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddscsi.h
api_name:
-	HYBRID_INFORMATION
product: Windows
targetos: Windows
req.typenames: HYBRID_INFORMATION, *PHYBRID_INFORMATION
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


`Version`

The version of this structure. Set to HYBRID_REQUEST_INFO_STRUCTURE_VERSION.

`Size`

The size of this structure. Set to <b>sizeof</b>(HYBRID_INFORMATION).

`HybridSupported`

Miniport supports for hybrid disks. Set to <b>TRUE</b> if hybrid disks are supported. Otherwise, <b>FALSE</b>.

`Status`

The status of the hybrid disk cache. This contains one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NvCacheStatusUnknown"></a><a id="nvcachestatusunknown"></a><a id="NVCACHESTATUSUNKNOWN"></a><dl>
<dt><b>NvCacheStatusUnknown</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver is not able to report the cache status.

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheStatusDisabling"></a><a id="nvcachestatusdisabling"></a><a id="NVCACHESTATUSDISABLING"></a><dl>
<dt><b>NvCacheStatusDisabling</b></dt>
</dl>
</td>
<td width="60%">
The cache is currently changing to <b>NvCacheStatusDisabled</b> status.

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheStatusDisabled"></a><a id="nvcachestatusdisabled"></a><a id="NVCACHESTATUSDISABLED"></a><dl>
<dt><b>NvCacheStatusDisabled</b></dt>
</dl>
</td>
<td width="60%">
The cache on the hybrid disk is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheStatusEnabled"></a><a id="nvcachestatusenabled"></a><a id="NVCACHESTATUSENABLED"></a><dl>
<dt><b>NvCacheStatusEnabled</b></dt>
</dl>
</td>
<td width="60%">
The cache on the hybrid disk is enabled.

</td>
</tr>
</table>

`CacheTypeEffective`

The non-volatile caching type currently set for hybrid disk. The effective cache type is one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NvCacheTypeUnknown"></a><a id="nvcachetypeunknown"></a><a id="NVCACHETYPEUNKNOWN"></a><dl>
<dt><b>NvCacheTypeUnknown</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver is not able to report the cache type

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheNone"></a><a id="nvcachenone"></a><a id="NVCACHENONE"></a><dl>
<dt><b>NvCacheNone</b></dt>
</dl>
</td>
<td width="60%">
The disk does not support a non-volatile cache.

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheTypeWriteBack"></a><a id="nvcachetypewriteback"></a><a id="NVCACHETYPEWRITEBACK"></a><dl>
<dt><b>NvCacheTypeWriteBack</b></dt>
</dl>
</td>
<td width="60%">
Write-back caching is supported by hybrid disk.

</td>
</tr>
<tr>
<td width="40%"><a id="NvCacheTypeWriteThrough"></a><a id="nvcachetypewritethrough"></a><a id="NVCACHETYPEWRITETHROUGH"></a><dl>
<dt><b>NvCacheTypeWriteThrough</b></dt>
</dl>
</td>
<td width="60%">
Write-through caching is supported by hybrid disk.

</td>
</tr>
</table>

`CacheTypeDefault`

The default caching type used by the hybrid disk. The possible values are the same as for <b>CacheTypeEffective</b>.

`FractionBase`

The base value for fractional fields in this structure. This value is set to 255.

`CacheSize`

The size, in LBAs, of the non-volatile on the hybrid disk.

`Attributes`

The hybrid disk attributes.



#### WriteCacheChangeable

Support for changes in write caching policy. The value is 1 policy changes are allowed. Otherwise, changes are ignored.



#### WriteThroughIoSupported

Support for individual write operations when write-through caching is used. The value is 1 if individual writes are supported. Otherwise, the values is 0.



#### FlushCacheSupported

Support for non-volatile cache flush. The value is 1 if flushes are supported. Otherwise, the value is 0.



#### Removable

Support of removal of the non-volatile cache from the disk. The value is 1 if the cache is removable. Otherwise, the value is 0.



#### ReservedBits

Reserved.

`Priorities`

Priority settings for the hybrid disk.



#### PriorityLevelCount

The number of priority levels supported by the cache. Currently, a non-zero value indicates support for all priorities.



#### MaxPriorityBehavior

If <b>TRUE</b>, the disk I/O can fail at maximum priority if the cache is full.  Otherwise, if <b>FALSE</b>, the operation will complete to disk.



#### DirtyThresholdLow

The low threshold for a cache flush. This value is ratio in the range of <b>FractionBase</b>.



#### DirtyThresholdHigh

The low threshold for a cache flush. This value is ratio in the range of <b>FractionBase</b>.



#### Priority

An array of priority level descriptors. The number of descriptors present in the array is set in <b>PriorityLevelCount</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_hybrid.md">IOCTL_SCSI_MINIPORT_HYBRID</a>