---
UID : NF:wdfdriver.WDF_DRIVER_CONFIG_INIT
title : WDF_DRIVER_CONFIG_INIT function
author : windows-driver-content
description : The WDF_DRIVER_CONFIG_INIT function initializes a driver's WDF_DRIVER_CONFIG structure.
old-location : wdf\wdf_driver_config_init.htm
old-project : wdf
ms.assetid : d7520300-9345-4681-a10d-acf34838199a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WDF_DRIVER_CONFIG_INIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdriver.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WDF_DRIVER_CONFIG_INIT
req.alt-loc : wdfdriver.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : WDF_DRIVER_INIT_FLAGS
req.product : Windows 10 or later.
---


# WDF_DRIVER_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_CONFIG_INIT function initializes a driver's <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure.

## Syntax

````
VOID WDF_DRIVER_CONFIG_INIT(
  _Out_    PWDF_DRIVER_CONFIG        Config,
  _In_opt_ PFN_WDF_DRIVER_DEVICE_ADD EvtDriverDeviceAdd
);
````

## Parameters

`Config`

A pointer to the <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure that the function will initialize.

`EvtDriverDeviceAdd`

A pointer to the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


## Return Value

None

## Remarks

The WDF_DRIVER_CONFIG_INIT function is available in version 1.0 and later versions of KMDF.

For a code example that uses WDF_DRIVER_CONFIG_INIT, see <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdriver.h (include Wdf.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DRIVER_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>