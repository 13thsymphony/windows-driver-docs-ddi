---
UID: NS:dispmprt._DXGK_TIMED_OPERATION_INTERFACE
title: "_DXGK_TIMED_OPERATION_INTERFACE"
author: windows-driver-content
description: The DXGK_TIMED_OPERATION_INTERFACE structure contains pointers to functions in the Timed Operation Interface, which is implemented by the display port driver.
old-location: display\dxgk_timed_operation_interface.htm
old-project: display
ms.assetid: 85b3764d-00b5-4e1d-bedc-c59a6b182735
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_TIMED_OPERATION_INTERFACE, DXGK_TIMED_OPERATION_INTERFACE, DXGK_TIMED_OPERATION_INTERFACE structure [Display Devices], DmStructs_024c0974-7f10-4251-b08e-c68307fc62d9.xml, PDXGK_TIMED_OPERATION_INTERFACE, PDXGK_TIMED_OPERATION_INTERFACE structure pointer [Display Devices], _DXGK_TIMED_OPERATION_INTERFACE, display.dxgk_timed_operation_interface, dispmprt/DXGK_TIMED_OPERATION_INTERFACE, dispmprt/PDXGK_TIMED_OPERATION_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_TIMED_OPERATION_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_TIMED_OPERATION_INTERFACE, *PDXGK_TIMED_OPERATION_INTERFACE
---

# _DXGK_TIMED_OPERATION_INTERFACE structure
The DXGK_TIMED_OPERATION_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>, which is implemented by the display port driver.

## Syntax
````
typedef struct _DXGK_TIMED_OPERATION_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  NTSTATUS               (*TimedOperationStart)(
      _Out_ DXGK_TIMED_OPERATION *Op, 
      _In_ const LARGE_INTEGER *Timeout, 
      _In_ BOOLEAN OsHandled);
  NTSTATUS               (*TimedOperationDelay)(
      _Inout_ DXGK_TIMED_OPERATION *Op, 
      _In_ KPROCESSOR_MODE WaitMode, 
      _In_ BOOLEAN Alertable, 
      _In_opt_ const LARGE_INTEGER *Interval);
  NTSTATUS               (*TimedOperationWaitForSingleObject)(
      _Inout_ DXGK_TIMED_OPERATION *Op, 
      _In_ PVOID Object, 
      _In_ KWAIT_REASON WaitReason, 
      _In_ KPROCESSOR_MODE WaitMode, 
      _In_ BOOLEAN Alertable, 
      _In_opt_ const LARGE_INTEGER *Timeout);
} DXGK_TIMED_OPERATION_INTERFACE, *PDXGK_TIMED_OPERATION_INTERFACE;
````

## Members


`Context`

A pointer to a context that is provided by the display port driver.

`InterfaceDereference`

A pointer to an interface dereference function that is implemented by the display port driver.

`InterfaceReference`

A pointer to an interface reference function that is implemented by the display port driver.

`Size`

The size, in bytes, of this structure.

`TimedOperationDelay`

The <b>TimedOperationDelay</b> function puts the current thread into an alertable or nonalertable wait state for a given interval with regard to the given timed operation time-out.



#### Op

[in/out] A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_timed_operation.md">DXGK_TIMED_OPERATION</a> structure that describes the timed operation to delay. This timed operation was started by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> function.



#### WaitMode

[in] A KPROCESSOR_MODE-typed value that specifies the processor mode the driver waits in. The value can be either <b>KernelMode</b> or <b>UserMode</b>. Lower-level drivers in a stack should specify <b>KernelMode</b>.



#### Alertable

[in] A Boolean value that specifies whether the wait is alertable. A value of <b>TRUE</b> indicates that the wait is alertable; <b>FALSE</b> indicates that the wait is nonalertable. Lower-level drivers in a stack should specify <b>FALSE</b>.



#### Interval

[in] A pointer to variable that contains the relative time, in 100-nanoseconds units, for the delay. The sign of the value is ignored.

`TimedOperationStart`

The <b>TimedOperationStart</b> function starts or restarts a timed operation.

The driver should preset the <b>Size</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgk_timed_operation.md">DXGK_TIMED_OPERATION</a> structure that is pointed to by the <i>Op</i> parameter to <b>sizeof</b>(DXGK_TIMED_OPERATION).



#### Op

[out] A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_timed_operation.md">DXGK_TIMED_OPERATION</a> structure that describes the timed operation to start or restart.



#### Timeout

[in] A pointer to a time-out value, in 100-nanoseconds units, that specifies the relative time that was allotted for the timed operation to complete. 



#### OsHandled

A Boolean value that specifies whether the operating system handles the time-out condition. A value of <b>TRUE</b> indicates that the driver does not have any reasonable way to handle the time-out condition and lets the operating system handle the time-out condition; <b>FALSE</b> indicates that the driver handles the time-out condition.

`TimedOperationWaitForSingleObject`

The <b>TimedOperationWaitForSingleObject</b> function puts the current thread into a wait state until the given dispatcher object is set to a signaled state or optionally until the wait times out or until the time-out of the given timed operation expires.



#### Op

[in] A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_timed_operation.md">DXGK_TIMED_OPERATION</a> structure that describes the timed operation to put into a wait state. This timed operation was started by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> function.



#### Object

A pointer to an initialized dispatcher object that the caller supplies the storage for. The dispatcher object can be an event, a mutex, a semaphore, a thread, or a timer. 



#### WaitReason

A KWAIT_REASON-typed value that specifies the reason for the wait. A driver should set this value to <b>Executive</b> or, if the driver is doing work on behalf of a user and is running in the context of a user thread, to <b>UserRequest</b>.



#### WaitMode

A KPROCESSOR_MODE-typed value that specifies the processor mode the driver waits in. The value can be either <b>KernelMode</b> or <b>UserMode</b>. Lowest-level and intermediate drivers should specify <b>KernelMode</b>. If the object that is pointed to by the <i>Object</i> parameter is a mutex, the caller must specify <b>KernelMode</b>. 



#### Alertable

A Boolean value that specifies whether the wait is alertable. A value of <b>TRUE</b> indicates that the wait is alertable; <b>FALSE</b> indicates that the wait is nonalertable. 



#### Timeout

A pointer to variable that contains the relative time, in 100-nanoseconds units, for the wait to be completed. The sign of the value is ignored.

`Version`

The version number of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_TIMED_OPERATION_INTERFACE_VERSION_1).

## Remarks
The display miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>, which fills in the remaining members of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_TIMED_OPERATION_INTERFACE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>