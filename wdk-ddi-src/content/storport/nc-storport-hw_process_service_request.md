---
UID : NC:storport.HW_PROCESS_SERVICE_REQUEST
title : HW_PROCESS_SERVICE_REQUEST
author : windows-driver-content
description : The HwStorProcessServiceRequest callback routine receives the device control IRP that contains the IOCTL_MINIPORT_PROCESS_SERVICE_IRP request when a caller, such as a user-mode application or kernel-mode driver, requires a &#0034;reverse callback&#0034; operation.
old-location : storage\hwstorprocessservicerequest.htm
old-project : storage
ms.assetid : bdcaf9a7-4c79-407b-bec4-182f3a1d1f37
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HwStorProcessServiceRequest
req.alt-loc : Storport.h
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
req.typenames : "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product : Windows 10 or later.
---


# HW_PROCESS_SERVICE_REQUEST callback function
The <b>HwStorProcessServiceRequest</b> callback routine receives the device control  IRP that contains the  <a href="..\ntddscsi\ni-ntddscsi-ioctl_miniport_process_service_irp.md">IOCTL_MINIPORT_PROCESS_SERVICE_IRP</a> request when a caller, such as a user-mode application or kernel-mode driver, requires a "reverse callback" operation. The I/O is completed by the miniport driver when it needs to tell the caller of something or needs the caller to do something.

## Syntax

```
HW_PROCESS_SERVICE_REQUEST HwProcessServiceRequest;

void HwProcessServiceRequest(
  PVOID DeviceExtension,
  PVOID Irp
)
{...}
```

## Parameters

`DeviceExtension`

A pointer to the virtual miniport driver's per-adapter storage area.

`Irp`

A pointer to the I/O request.


## Return Value

None

## Remarks

The name <b>HwStorProcessServiceRequest</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

The port driver calls the Storport virtual miniport driver's <b>HwStorProcessServiceRequest</b> routine at PASSIVE_LEVEL. The virtual miniport driver completes the IRP by calling the <a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a> routine.

To define an <b>HwStorProcessServiceRequest</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorProcessServiceRequest</b> callback routine that is named <i>MyHwProcessServiceRequest</i>, use the <b>HW_PROCESS_SERVICE_REQUEST</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>HW_PROCESS_SERVICE_REQUEST</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_PROCESS_SERVICE_REQUEST</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_miniport_process_service_irp.md">IOCTL_MINIPORT_PROCESS_SERVICE_IRP</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorProcessServiceRequest routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>