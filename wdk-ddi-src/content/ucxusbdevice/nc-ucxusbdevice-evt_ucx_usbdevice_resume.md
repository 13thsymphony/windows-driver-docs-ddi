---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_RESUME
title: EVT_UCX_USBDEVICE_RESUME function
author: windows-driver-content
description: UCX invokes this callback function to resume a device from suspend state.
old-location: buses\evt_ucx_usbdevice_resume.htm
old-project: usbref
ms.assetid: 876D9754-B3AA-42C5-8BDD-60CFD4F78951
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: EVT_UCX_USBDEVICE_RESUME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: *PFN_UCX_USBDEVICE_RESUME
req.alt-loc: ucxusbdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_RESUME function



## -description
UCX invokes this callback function to resume a device from suspend state.



## -syntax

````
EVT_UCX_USBDEVICE_RESUME EvtUcxDeviceResume;

void EvtUcxDeviceResume(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXUSBDEVICE  UcxUsbDevice
)
{ ... }

typedef EVT_UCX_USBDEVICE_RESUME *PFN_UCX_USBDEVICE_RESUME;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device that the client driver received in a previous call to the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.


## -returns
This callback function does not return a value.


## -remarks
The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.</p>