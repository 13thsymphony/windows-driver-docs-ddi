---
UID: NF:portcls.PcUnregisterAdapterPnpManagement
title: PcUnregisterAdapterPnpManagement function
author: windows-driver-content
description: The PcUnregisterAdapterPnpManagement function unregisters the audio adapter's PnP management interface from the PortCls class driver. It is used to support PnP rebalance.
old-location: audio\pcunregisteradapterpnpmanagement.htm
old-project: audio
ms.assetid: 51BBE9F6-7661-45A1-8416-9AAA307FCA10
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PcUnregisterAdapterPnpManagement, PcUnregisterAdapterPnpManagement function [Audio Devices], audio.pcunregisteradapterpnpmanagement, portcls/PcUnregisterAdapterPnpManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcUnregisterAdapterPnpManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcUnregisterAdapterPnpManagement function
The <b>PcUnregisterAdapterPnpManagement</b> function unregisters the audio adapter's PnP management interface from the PortCls class driver.  It is used to support PnP rebalance.

## Syntax

````
PORTCLASSAPI NTSTATUS NTAPI PcUnregisterAdapterPnpManagement(
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## Return Value

The <b>PcUnregisterAdapterPnpManagement</b>  function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.

## Remarks

The <b>PcUnregisterAdapterPnpManagement</b>  function unregisters a driver's PnP management interface that was registered with PortCls by using the <b>PcUnregisterAdapterPnpManagement</b>  function. 

 This function must only be called if the PnP management interface for the adapter was previously registered with PortCls using <a href="..\portcls\nf-portcls-pcregisteradapterpnpmanagement.md">PcRegisterAdapterPnpManagement</a>.

Portcls uses <a href="..\portcls\nf-portcls-pcregisteradapterpnpmanagement.md">PcRegisterAdapterPnpManagement</a> and <b>PcUnregisterAdapterPnpManagement</b> to support PNP rebalance. 


For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1511 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nf-portcls-pcregisteradapterpnpmanagement.md">PcRegisterAdapterPnpManagement</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>