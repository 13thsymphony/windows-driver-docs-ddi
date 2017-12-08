---
UID: NF.storport.StorPortSetDeviceQueueDepth
title: StorPortSetDeviceQueueDepth function
author: windows-driver-content
description: The StorPortSetDeviceQueueDepth routine sets the maximum depth of the device queue for the indicated device.
old-location: storage\storportsetdevicequeuedepth.htm
old-project: storage
ms.assetid: e79b4294-5ba4-4fcc-97e2-69613b65f574
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortSetDeviceQueueDepth
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
req.alt-api: StorPortSetDeviceQueueDepth
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

# StorPortSetDeviceQueueDepth function



## -description
The <b>StorPortSetDeviceQueueDepth</b> routine sets the maximum depth of the device queue for the indicated device. 


## -syntax

````
STORPORT_API BOOLEAN StorPortSetDeviceQueueDepth(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ ULONG Depth
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 

### -param PathId [in]

Contains the path ID of the target device. 

### -param TargetId [in]

Contains the device number of the target device. 

### -param Lun [in]

Contains the logical unit number of the target device. 

### -param Depth [in]

Supplies the depth to which the queue is to be set. This value is always &gt; 0.

## -returns
<b>StorPortSetDeviceQueueDepth</b> returns <b>TRUE</b> if the queue depth was successfully set, or <b>FALSE</b> if the operation failed. 

## -remarks
Before the first call to <b>StorPortSetDeviceQueueDepth</b>, the device queue depth is set to the default value. The following conditional description determines the default queue depth.

The <b>StorPortSetDeviceQueueDepth</b> routine should be called when the miniport driver receives the first SCSI Inquiry command for the specified LUN, or at any time thereafter (but not before), as long as the LUN is valid.

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