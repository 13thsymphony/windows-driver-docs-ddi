---
UID: NF:storport.StorPortFreeDeviceBase
title: StorPortFreeDeviceBase function
author: windows-driver-content
description: StorPortFreeDeviceBase frees a range of device I/O memory that was mapped by StorPortGetDeviceBase.
old-location: storage\storportfreedevicebase.htm
old-project: storage
ms.assetid: 4feb3bde-c243-493c-a6f9-4accd545955c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortFreeDeviceBase
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
req.alt-api: StorPortFreeDeviceBase
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreeDeviceBase function



## -description
<b>StorPortFreeDeviceBase</b> frees a range of device I/O memory that was mapped by <a href="..\storport\nf-storport-storportgetdevicebase.md">StorPortGetDeviceBase</a>.



## -syntax

````
STORPORT_API VOID StorPortFreeDeviceBase(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID MappedAddress
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param MappedAddress [in]

Pointer to region of memory to be freed.


## -returns
None 


## -remarks


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
<a href="..\storport\nf-storport-storportgetdevicebase.md">StorPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportfreedevicebase.md">ScsiPortFreeDeviceBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeDeviceBase function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

