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
ms.keywords : storage.hwstorprocessservicerequest, HwStorProcessServiceRequest routine [Storage Devices], HwStorProcessServiceRequest, HW_PROCESS_SERVICE_REQUEST, HW_PROCESS_SERVICE_REQUEST, storport/HwStorProcessServiceRequest, storvmini_50b0d1a2-74bf-4ee4-a9f7-3c30f1a81507.xml
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
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
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_PROCESS_SERVICE_REQUEST (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  Irp
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the Storport virtual miniport driver's <b>HwStorProcessServiceRequest</b> routine at PASSIVE_LEVEL. The virtual miniport driver completes the IRP by calling the <a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_miniport_process_service_irp.md">IOCTL_MINIPORT_PROCESS_SERVICE_IRP</a>

<a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorProcessServiceRequest routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>