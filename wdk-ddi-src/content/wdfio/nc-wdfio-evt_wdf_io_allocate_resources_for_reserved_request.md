---
UID : NC:wdfio.EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST
title : EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST
author : windows-driver-content
description : A driver's EvtIoAllocateResourcesForReservedRequest callback function allocates request-specific resources that the driver can use to process an I/O request in the future.
old-location : wdf\evtioallocateresourcesforreservedrequest.htm
old-project : wdf
ms.assetid : 07ba6437-655b-417a-87a8-5374812ca4d7
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtioallocateresourcesforreservedrequest, EvtIoAllocateResourcesForReservedRequest callback function, EvtIoAllocateResourcesForReservedRequest, EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST, EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST, wdfio/EvtIoAllocateResourcesForReservedRequest, DFQueueObjectRef_7fafb899-1038-409b-af8e-f45776b18abe.xml, kmdf.evtioallocateresourcesforreservedrequest
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfio.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.9
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
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product : Windows 10 or later.
---


# EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST function
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtIoAllocateResourcesForReservedRequest</i> callback function allocates request-specific resources that the driver can use to process an I/O request in the future. The framework is pre-allocating the specified request object for future use in low-memory situations.

## Syntax

```
EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST EvtWdfIoAllocateResourcesForReservedRequest;

NTSTATUS EvtWdfIoAllocateResourcesForReservedRequest(
  WDFQUEUE Queue,
  WDFREQUEST Request
)
{...}
```

## Parameters

`Queue`

A handle to an I/O queue object.

`Request`

A handle to a request object that the framework has created for use during future low-memory situations.


## Return Value

The <i>EvtIoAllocateResourcesForReservedRequest</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## Remarks

A driver can register an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function, the framework calls the function immediately after it creates a request object that it reserves for low-memory situations. 

The callback function can allocate resources that your driver will require to process a request later, if the framework uses the reserved request because of a low-memory situation.

To allocate memory for request-specific resources, an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function might call <a href="..\wdfobject\nf-wdfobject-wdfobjectallocatecontext.md">WdfObjectAllocateContext</a>, specifying the request object handle that the <i>Request</i> parameter specifies. 

Alternatively or additionally, your driver might call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. As a result, the framework will allocate context space for each reserved request object when it creates the object. 

If your driver allocates object context space for reserved request objects, the driver must reinitialize the context space when it completes an I/O request that uses a reserved request object. The framework does not reinitialize the context space of reserved request objects after use.

If your driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a> and specifies an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback function for its request objects, the framework calls these callback functions for its reserved request objects only when it deletes the associated I/O queues.

The driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a> can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestisreserved.md">WdfRequestIsReserved</a> to determine if reserved request objects are being used.

For more information about how to use object context space, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

If the callback function successfully allocates resources, it should return STATUS_SUCCESS.

If a resource allocation error occurs, such as a low memory situation, the callback function must return an error status value. In this case, the framework stops allocating reserved request objects and uses the callback function's return value as the return value for <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>.

For more information about the <i>EvtIoAllocateResourcesForReservedRequest</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.9 |
| **Minimum UMDF version** |  |
| **Header** | wdfio.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestisreserved.md">WdfRequestIsReserved</a>

<a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>

<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_request_resources.md">EvtIoAllocateRequestResources</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>