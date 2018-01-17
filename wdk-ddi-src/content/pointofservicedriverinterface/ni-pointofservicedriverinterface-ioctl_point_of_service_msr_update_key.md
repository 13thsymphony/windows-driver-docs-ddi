---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
title: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
author: windows-driver-content
description: This I/O control function sets a new encryption key.
old-location: pos\ioctl_point_of_service_msr_update_key.htm
old-project: pos
ms.assetid: 7ac830d3-6a75-4d82-9123-cd7ad9c2cdea
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PosPropertyId, PosPropertyId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
req.alt-loc: pointofservicedriverinterface.h
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
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL



## -description
This I/O control function sets a new encryption key.



## -ioctlparameters

### -input-buffer
Pointer to the input buffer, a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_update_key.md">MSR_UPDATE_KEY</a> variable.


### -input-buffer-length
Size of the input buffer, in bytes. Set to <b>sizeof(MSR_UPDATE_KEY)</b>.


### -output-buffer
Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length
Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>


## -remarks
