---
UID: NF.storport.StorPortGetPhysicalAddress
title: StorPortGetPhysicalAddress function
author: windows-driver-content
description: The StorPortGetPhysicalAddress routine converts a given virtual address range to a physical address range for a DMA operation.
old-location: storage\storportgetphysicaladdress.htm
old-project: storage
ms.assetid: 2b39a6e4-2e11-4b4e-9218-92336629ae80
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortGetPhysicalAddress
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
req.alt-api: StorPortGetPhysicalAddress
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortGetPhysicalAddress function



## -description
The <b>StorPortGetPhysicalAddress</b> routine converts a given virtual address range to a physical address range for a DMA operation.


## -syntax

````
STORPORT_API STOR_PHYSICAL_ADDRESS StorPortGetPhysicalAddress(
  _In_     PVOID               HwDeviceExtension,
  _In_opt_ PSCSI_REQUEST_BLOCK Srb,
  _In_     PVOID               VirtualAddress,
  _Out_    ULONG               *Length
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the device object for the HBA immediately after the miniport driver calls <a href="storage.storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 

### -param Srb [in, optional]

Pointer to the SCSI request block if the virtual address to be converted comes from that SRB's <b>DataBuffer</b> member or <b>SenseInfoBuffer</b> member. Otherwise, this parameter must be <b>NULL</b>. 

### -param VirtualAddress [in]

Pointer to the base virtual address to be converted. If this virtual address falls within the range for an SRB-supplied <b>DataBuffer</b>, the caller also must provide the <i>Srb</i> pointer. 

### -param Length [out]

Pointer to a value indicating the number of bytes mapped, starting at the returned physical address.

## -returns
<b>StorPortGetPhysicalAddress</b> returns the corresponding physical address for a given virtual address. If the given address cannot be converted, the function returns <b>NULL</b>. 

## -remarks
If the virtual address passed to <b>StorPortGetPhysicalAddress</b> is obtained from <a href="storage.storportallocatecontiguousmemoryspecifycachenode">StorPortAllocateContiguousMemorySpecifyCacheNode</a>, the value returned for <i>Length</i> should be ignored.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="storage.storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

<b>StorPortGetPhysicalAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address. 

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
Library
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>
</dt>
<dt>
<a href="storage.storage_request_block">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetPhysicalAddress routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
