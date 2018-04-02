---
UID: NF:wdfdevice.WDF_IO_TYPE_CONFIG_INIT
title: WDF_IO_TYPE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_IO_TYPE_CONFIG_INIT function initializes a driver's WDF_IO_TYPE_CONFIG structure.
old-location: wdf\wdf_io_type_config_init.htm
old-project: wdf
ms.assetid: 45D60409-EAE5-43A0-9E90-0B2F9FC31840
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_IO_TYPE_CONFIG_INIT, WDF_IO_TYPE_CONFIG_INIT function, wdf.wdf_io_type_config_init, wdfdevice/WDF_IO_TYPE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_IO_TYPE_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WDF_IO_TYPE_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TYPE_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a> structure.

## Syntax

```
void WDF_IO_TYPE_CONFIG_INIT(
  PWDF_IO_TYPE_CONFIG IoTypeConfig
);
```

## Parameters

`IoTypeConfig`

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a> structure.


## Return Value

This function does not return a value.

## Remarks

The <b>WDF_IO_TYPE_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a> structure and sets the  structure's <b>Size</b> member. It then sets the <b>ReadWriteIoType</b> member to <b>WdfDeviceIoBuffered</b>, and the <b>DeviceControlIoType</b> member to <b>WdfDeviceIoBuffered</b>.


#### Examples

For a code example that uses <b>WDF_IO_TYPE_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265604">WdfDeviceInitSetIoTypeEx</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265604">WdfDeviceInitSetIoTypeEx</a>