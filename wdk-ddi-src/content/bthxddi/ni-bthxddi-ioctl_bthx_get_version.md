---
UID: NI:bthxddi.IOCTL_BTHX_GET_VERSION
title: IOCTL_BTHX_GET_VERSION
author: windows-driver-content
description: Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.
old-location: bltooth\ioctl_bthx_get_version.htm
old-project: bltooth
ms.assetid: F4FD760B-551C-4738-A13D-444E08215D59
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHX_GET_VERSION
req.alt-loc: BthXDDI.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT
---

# IOCTL_BTHX_GET_VERSION IOCTL



## -description

Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.



Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> method to retrieve output parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &amp;ReqOutMemory);</code>

The buffer describes a <a href="..\bthxddi\ns-bthxddi-_bthx_version.md">BTHX_VERSION</a> structure. 

Refer to the WDK Bluetooth samples for more information.


### -output-buffer-length
The length of the buffer is the size of the <b>BTHX_VERSION</b> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that holds the BTHX_VERSION structure.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

 

Any unsuccessful NT status code prevents the driver from loading.


## -remarks
IOCTL_BTHX_GET_VERSION is a synchronous operation.

A transport driver can return one or more versions that it supports in BTHX_VERSION structure.  If no version is set,  Windows unloads the Bluetooth stack.</p>