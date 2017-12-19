---
UID: NF.storport.StorPortAllocateHostMemoryBuffer
title: StorPortAllocateHostMemoryBuffer function
author: windows-driver-content
description: This function allocates one or more ranges of physically contiguous memory to be used as a Host Memory Buffer (HMB).
old-location: storage\storportallocatehostmemorybuffer.htm
old-project: storage
ms.assetid: B8413B02-32A6-40AE-9DD2-C25AD2D2D45C
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortAllocateHostMemoryBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortAllocateHostMemoryBuffer
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# StorPortAllocateHostMemoryBuffer function



## -description
This function allocates one or more ranges of physically contiguous memory
    to be used as a Host Memory Buffer (HMB).  This is memory that the device
    may use directly and exclusively.  The device may use this memory however
    it sees fit, but it must ensure that there is no data loss or data
    corruption in the event of a surprise removal or unexpected power loss.

Depending on the allocation policy, this function may allocate as much as
    the device's preferred size, as little as the device's minimum size, or no
    memory at all.

    This function will attempt to allocate as few physically contiguous address
    ranges as possible, but it may have to use multiple physical address ranges
    to satisfy the desired HMB size.




## -syntax

````
ULONG StorPortAllocateHostMemoryBuffer(
  _In_     PVOID                                                                                 HwDeviceExtension,
  _In_     SIZE_T                                                                                MinimumBytes,
  _In_     SIZE_T                                                                                PreferredBytes,
  _In_     ULONGLONG                                                                             UtilizationBytes,
  _In_     ULONG                                                                                 AlignmentBytes,
  _In_     PHYSICAL_ADDRESS                                                                      LowestAcceptableAddress,
  _In_     PHYSICAL_ADDRESS                                                                      HighestAcceptableAddress,
  _In_opt_ PHYSICAL_ADDRESS                                                                      BoundaryAddressMultiple,
           _Out_writes_to_(*PhysicalAddressRangeCount, *PhysicalAddressRangeCount) PACCESS_RANGE PhysicalAddressRanges,
  _Inout_  PULONG                                                                                PhysicalAddressRangeCount
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MinimumBytes [in]

The minimum amount of memory that will be useful to the
        device, in bytes. A value of 0 indicates that any size of memory up to
        the preferred size is acceptable.


### -param PreferredBytes [in]

The amount of memory the device prefers, in bytes.  This
        must be a multiple of the page size.


### -param UtilizationBytes [in]

The total number of blocks allocated on the device, in
        bytes.


### -param AlignmentBytes [in]

The Host Memory Buffer alignment requirement from the device.


### -param LowestAcceptableAddress [in]

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).


### -param HighestAcceptableAddress [in]

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).


### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that this allocation must not cross.

<div class="alert"><b>Note</b>  This parameter is currently not used and must be set to 0.</div>
<div> </div>

### -param PhysicalAddressRanges 

An array of physical address ranges that make up
        the Host Memory Buffer.  The caller should provide a pre-allocated array.  <b>StorPortAllocateHostMemoryBuffer</b> will
        fill in the array with one or more physical address ranges.


### -param PhysicalAddressRangeCount [in, out]

 The number of entries in <b>PhysicalAddressRanges</b>. This function will update this parameter to indicate how
        many physical address ranges it filled in.


## -returns
<b>StorPortAllocateHostMemoryBuffer</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The <b>PhysicalAddressRanges</b> array contains one or more valid physical address ranges that represent the host memory buffer.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>This could indicate a minimum value that is greater than a maximum value, a non-page-aligned size, or that <b>PhysicalAddressRanges</b> is empty.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The host memory buffer could not be allocated.

 


## -remarks

        
      The caller should subsequently call <a href="storage.StorPortFreeHostMemoryBuffer">StorPortFreeHostMemoryBuffer</a> when it is
    done with the host memory buffer.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">


</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.StorPortFreeHostMemoryBuffer">StorPortFreeHostMemoryBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortAllocateHostMemoryBuffer routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

