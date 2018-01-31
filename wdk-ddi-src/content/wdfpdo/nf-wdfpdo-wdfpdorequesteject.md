---
UID : NF:wdfpdo.WdfPdoRequestEject
title : WdfPdoRequestEject function
author : windows-driver-content
description : The WdfPdoRequestEject method informs the framework that a specified device is about to be ejected from its docking station.
old-location : wdf\wdfpdorequesteject.htm
old-project : wdf
ms.assetid : 40cd83c0-701a-436f-a3c3-b0ab14848a92
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DFDeviceObjectFdoPdoRef_f57ccd07-8cb3-4972-bddb-aa704d9422b0.xml, wdf.wdfpdorequesteject, kmdf.wdfpdorequesteject, wdfpdo/WdfPdoRequestEject, PFN_WDFPDOREQUESTEJECT, WdfPdoRequestEject method, WdfPdoRequestEject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfpdo.h
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product : Windows 10 or later.
---


# WdfPdoRequestEject function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRequestEject</b> method informs the framework that a specified device is about to be ejected from its docking station.

## Syntax

````
VOID WdfPdoRequestEject(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object that represents the device's physical device object (PDO).


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

A bus driver can call <b>WdfPdoRequestEject</b> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a> to report that the driver has detected an attempt to eject one of its enumerated child devices from the device's docking station. For example, the driver might detect that a user has pushed an eject button. 

If the framework device object for the device's PDO is available, the driver can call <b>WdfPdoRequestEject</b>. If the driver is using dynamic bus enumeration and if the device's identification description is available, the driver can call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>.

For more information about <b>WdfPdoRequestEject</b> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdffdo\nf-wdffdo-wdffdoretrievenextstaticchild.md">WdfFdoRetrieveNextStaticChild</a>

<a href="..\wdffdo\nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md">WdfFdoUnlockStaticChildListFromIteration</a>

<a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoRequestEject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>