---
UID : NF:wdffdo.WdfFdoRetrieveNextStaticChild
title : WdfFdoRetrieveNextStaticChild function
author : windows-driver-content
description : The WdfFdoRetrieveNextStaticChild method retrieves a handle to the next framework device object in a list of child devices.
old-location : wdf\wdffdoretrievenextstaticchild.htm
old-project : wdf
ms.assetid : ee0f458b-c8b3-46e7-87bd-25599d39203d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfFdoRetrieveNextStaticChild method, wdffdo/WdfFdoRetrieveNextStaticChild, WdfFdoRetrieveNextStaticChild, DFDeviceObjectFdoPdoRef_013cf620-08fe-4c72-8a5e-c7e38a37b503.xml, PFN_WDFFDORETRIEVENEXTSTATICCHILD, kmdf.wdffdoretrievenextstaticchild, wdf.wdffdoretrievenextstaticchild
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdffdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
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
req.typenames : "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
req.product : Windows 10 or later.
---


# WdfFdoRetrieveNextStaticChild function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoRetrieveNextStaticChild</b> method retrieves a handle to the next framework device object in a list of child devices.

## Syntax

````
WDFDEVICE WdfFdoRetrieveNextStaticChild(
  _In_     WDFDEVICE Fdo,
  _In_opt_ WDFDEVICE PreviousChild,
  _In_     ULONG     Flags
);
````

## Parameters

`Fdo`

A handle to a framework device object that represents the parent device.

`PreviousChild`

A handle to a framework device object that represents the child device that was returned by a previous call to <b>WdfFdoRetrieveNextStaticChild</b>. For the first call to <b>WdfFdoRetrieveNextStaticChild</b>, this value must be <b>NULL</b>.

`Flags`

A <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>-typed enumerator value that identifies the type of child devices that the method should retrieve. This parameter cannot be zero.


## Return Value

If the operation succeeds, the method returns a handle to a framework device object. Otherwise it returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Bus drivers that use static bus enumeration can call <b>WdfFdoRetrieveNextStaticChild</b>. 

To retrieve the items in a list of child devices, the driver should:
<ol>
<li>
Call <a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a> to lock the child list.

</li>
<li>
Repeatedly call <b>WdfFdoRetrieveNextStaticChild</b> to obtain the items in the list, one at a time, until the method returns <b>NULL</b>.

</li>
<li>
Call <a href="..\wdffdo\nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md">WdfFdoUnlockStaticChildListFromIteration</a> to unlock the child list.

</li>
</ol>For more information about static child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdffdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI |

## See Also

<a href="..\wdffdo\nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md">WdfFdoUnlockStaticChildListFromIteration</a>

<a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoRetrieveNextStaticChild method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>