---
UID : NS:wdfrequest._WDF_REQUEST_FORWARD_OPTIONS
title : "_WDF_REQUEST_FORWARD_OPTIONS"
author : windows-driver-content
description : The WDF_REQUEST_FORWARD_OPTIONS structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.
old-location : wdf\wdf_request_forward_options.htm
old-project : wdf
ms.assetid : 61ec4a05-749d-4d60-9bd7-ad121b6fd90f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : "_WDF_REQUEST_FORWARD_OPTIONS, kmdf.wdf_request_forward_options, DFRequestObjectRef_878a982e-6fe9-4bfc-ad5c-165ef7590b79.xml, PWDF_REQUEST_FORWARD_OPTIONS structure pointer, WDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS, PWDF_REQUEST_FORWARD_OPTIONS, WDF_REQUEST_FORWARD_OPTIONS structure, wdf.wdf_request_forward_options, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS, wdfrequest/PWDF_REQUEST_FORWARD_OPTIONS"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfrequest.h
req.include-header : Wdf.h
req.target-type : Windows
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS
req.product : Windows 10 or later.
---

# _WDF_REQUEST_FORWARD_OPTIONS structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.

## Syntax
````
typedef struct _WDF_REQUEST_FORWARD_OPTIONS {
  ULONG Size;
  ULONG Flags;
} WDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS;
````

## Members


`Flags`

A bitwise OR of <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_forward_options_flags.md">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>-typed flags.

`Size`

The size, in bytes, of this structure.

## Remarks
The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure is used as input to the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a> method.

Your driver must call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_forward_options_init.md">WDF_REQUEST_FORWARD_OPTIONS_INIT</a> to initialize the <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure before the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.9 |
| **Minimum UMDF version** |  |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="..\wdfrequest\ne-wdfrequest-_wdf_request_forward_options_flags.md">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_FORWARD_OPTIONS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>