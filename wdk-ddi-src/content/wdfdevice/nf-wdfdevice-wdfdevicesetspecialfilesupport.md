---
UID : NF:wdfdevice.WdfDeviceSetSpecialFileSupport
title : WdfDeviceSetSpecialFileSupport function
author : windows-driver-content
description : The WdfDeviceSetSpecialFileSupport method enables or disables a function driver's support for special files, for the specified device.
old-location : wdf\wdfdevicesetspecialfilesupport.htm
old-project : wdf
ms.assetid : 7648c486-181a-45c8-9c4b-e3158428046a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceSetSpecialFileSupport method, kmdf.wdfdevicesetspecialfilesupport, wdf.wdfdevicesetspecialfilesupport, PFN_WDFDEVICESETSPECIALFILESUPPORT, WdfDeviceSetSpecialFileSupport, DFDeviceObjectGeneralRef_c40463ef-3c26-431e-99d8-d176b0ef7ebf.xml, wdfdevice/WdfDeviceSetSpecialFileSupport
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceSetSpecialFileSupport function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetSpecialFileSupport</b> method enables or disables a function driver's support for special files, for the specified device.

## Syntax

````
VOID WdfDeviceSetSpecialFileSupport(
  _In_ WDFDEVICE             Device,
  _In_ WDF_SPECIAL_FILE_TYPE FileType,
  _In_ BOOLEAN               FileTypeIsSupported
);
````

## Parameters

`Device`

A handle to a framework device object.

`FileType`

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_special_file_type.md">WDF_SPECIAL_FILE_TYPE</a>-typed enumerator that identifies the type of special file that the driver supports.

`FileTypeIsSupported`

Supplies a Boolean value which, if <b>TRUE</b>, enables support for the special file type and, if <b>FALSE</b>, disables support the special file type.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A function driver typically calls <b>WdfDeviceSetSpecialFileSupport</b> from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

Each driver's support for special files is initially disabled until the driver calls <b>WdfDeviceSetSpecialFileSupport</b>.

For more information, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdfdevice\ne-wdfdevice-_wdf_special_file_type.md">WDF_SPECIAL_FILE_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetSpecialFileSupport method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>