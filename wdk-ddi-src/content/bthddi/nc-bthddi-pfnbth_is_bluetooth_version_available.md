---
UID : NC:bthddi.PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE
title : PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE
author : windows-driver-content
description : The IsBluetoothVersionAvailable function checks whether a given Bluetooth version is supported by the operating system.
old-location : bltooth\isbluetoothversionavailable.htm
old-project : bltooth
ms.assetid : 10662237-18b4-4f37-a704-985b2db0d689
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth.isbluetoothversionavailable, IsBluetoothVersionAvailable callback function [Bluetooth Devices], IsBluetoothVersionAvailable, PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE, PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE, bthddi/IsBluetoothVersionAvailable, bth_funcs_34a25a87-fa07-46dc-aeaa-411009990c8b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Desktop
req.target-min-winverclnt : Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PMPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE"
---


# PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE callback function
The 
  <i>IsBluetoothVersionAvailable</i> function checks whether a given Bluetooth version is supported by the
  operating system.

## Syntax

```
PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE PfnbthIsBluetoothVersionAvailable;

BOOLEAN PfnbthIsBluetoothVersionAvailable(
  UCHAR MajorVersion,
  UCHAR MinorVersion
)
{...}
```

## Parameters

`MajorVersion`

This parameter specifies the major version number of Bluetooth that is requested.

`MinorVersion`

This parameter specifies the minor version number of Bluetooth that is requested.


## Return Value

<i>IsBluetoothVersionAvailable</i> returns <b>TRUE</b> if the Bluetooth version that the operating system
     provides is greater than or equal to the Bluetooth version number that is being requested.

## Remarks

Bluetooth profile drivers should call this function before performing any operations that are not
    supported in all Bluetooth versions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Target Platform** | Desktop |
| **Header** | bthddi.h (include Bthddi.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |