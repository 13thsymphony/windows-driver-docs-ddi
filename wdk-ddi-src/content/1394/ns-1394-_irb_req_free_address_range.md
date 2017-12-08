---
UID: NS.1394._IRB_REQ_FREE_ADDRESS_RANGE
title: _IRB_REQ_FREE_ADDRESS_RANGE
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 stack to carry out a free address range reqeust.
old-location: ieee\irb_req_free_address_range.htm
old-project: IEEE
ms.assetid: 18C1A210-6C6D-4BA7-AE62-81774DD62C58
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _IRB_REQ_FREE_ADDRESS_RANGE, IRB_REQ_FREE_ADDRESS_RANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_FREE_ADDRESS_RANGE
req.alt-loc: 1394.h
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

# _IRB_REQ_FREE_ADDRESS_RANGE structure



## -description
This structure contains the fields necessary for the 1394 stack to carry out a free address range reqeust.


## -syntax

````
typedef struct _IRB_REQ_FREE_ADDRESS_RANGE {
  ULONG          nAddressesToFree;
  PADDRESS_RANGE p1394AddressRange;
  PHANDLE        pAddressRange;
  PVOID          DeviceExtension;
} IRB_REQ_FREE_ADDRESS_RANGE;
````


## -struct-fields

### -field nAddressesToFree

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536908">ADDRESS_RANGE</a> structures pointed to by <b>IRB.u.FreeAddressRange.p1394AddressRange</b>

### -field p1394AddressRange

Specifies a pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536908">ADDRESS_RANGE</a> data structures to be released. These address ranges were returned in a prior successful call to <b>AllocateAddressRange</b>.

### -field pAddressRange

Points to the handle that was previously received in <b>IRB.u.AllocateAddressRange.hAddressRange</b> in the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a> request.

### -field DeviceExtension

Points to the device extension associated with the device object. Not setting this member can lead to unexpected behavior when the driver tries to access the allocated address space. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1394.h</dt>
</dl>
</td>
</tr>
</table>