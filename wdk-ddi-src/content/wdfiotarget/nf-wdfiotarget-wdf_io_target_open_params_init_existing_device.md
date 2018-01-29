---
UID : NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
title : WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function
author : windows-driver-content
description : The WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so that the driver can open a remote I/O target by specifying a Windows Driver Model (WDM) device object.
old-location : wdf\wdf_io_target_open_params_init_existing_device.htm
old-project : wdf
ms.assetid : 41fc4479-98e4-4632-89a1-1638eff02279
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DFIOTargetRef_fdd5195f-e259-4c89-b55e-e6ad06492a4d.xml, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE, kmdf.wdf_io_target_open_params_init_existing_device, wdf.wdf_io_target_open_params_init_existing_device, WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE, WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfiotarget.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE"
req.product : Windows 10 or later.
---


# WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b> function initializes a driver's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure so that the driver can open a remote I/O target by specifying a Windows Driver Model (WDM) device object.

## Syntax

````
VOID WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE(
  _Out_ PWDF_IO_TARGET_OPEN_PARAMS Params,
  _In_  PDEVICE_OBJECT             DeviceObject
);
````

## Parameters

`Params`

A pointer to a driver-allocated <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure that the function initializes.

`DeviceObject`

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure, which is used as the value for the <b>DeviceObject</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.


## Return Value

None

## Remarks

The <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> method.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b> function initializes the <b>Size</b>, <b>Type</b>, and <b>TargetDeviceObject</b> members of the specified <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

Typically, a driver sets the <b>TargetFileObject</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure after the driver has called <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_create_by_name.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</a>

<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>