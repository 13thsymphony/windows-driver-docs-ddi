---
UID: NS:wdfrequest._WDF_REQUEST_PARAMETERS
title: "_WDF_REQUEST_PARAMETERS"
author: windows-driver-content
description: The WDF_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O request.
old-location: wdf\wdf_request_parameters.htm
old-project: wdf
ms.assetid: 012e34c0-3cc6-49dc-94ad-d359d857720f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_request_parameters, wdfrequest/PWDF_REQUEST_PARAMETERS, WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS, wdfrequest/WDF_REQUEST_PARAMETERS, PWDF_REQUEST_PARAMETERS structure pointer, DFRequestObjectRef_b3f1759e-7bdd-4222-8aea-502bd45e16bf.xml, _WDF_REQUEST_PARAMETERS, WDF_REQUEST_PARAMETERS structure, wdf.wdf_request_parameters, PWDF_REQUEST_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_PARAMETERS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_PARAMETERS structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_PARAMETERS</b> structure receives parameters that are associated with an I/O request.

## Syntax
````
typedef struct _WDF_REQUEST_PARAMETERS {
  USHORT           Size;
  UCHAR            MinorFunction;
  WDF_REQUEST_TYPE Type;
  union {
    struct {
      PIO_SECURITY_CONTEXT     SecurityContext;
      ULONG                    Options;
      USHORT POINTER_ALIGNMENT FileAttributes;
      USHORT                   ShareAccess;
      ULONG POINTER_ALIGNMENT  EaLength;
    } Create;
    struct {
      size_t                  Length;
      ULONG POINTER_ALIGNMENT Key;
      LONGLONG                DeviceOffset;
    } Read;
    struct {
      size_t                  Length;
      ULONG POINTER_ALIGNMENT Key;
      LONGLONG                DeviceOffset;
    } Write;
    struct {
      size_t                   OutputBufferLength;
      size_t POINTER_ALIGNMENT InputBufferLength;
      ULONG POINTER_ALIGNMENT  IoControlCode;
      PVOID                    Type3InputBuffer;
    } DeviceIoControl;
    struct {
      PVOID                   Arg1;
      PVOID                   Arg2;
      ULONG POINTER_ALIGNMENT IoControlCode;
      PVOID                   Arg4;
    } Others;
  } Parameters;
} WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS;
````

## Members


`MinorFunction`

The IRP minor function code, if any, that is associated with the I/O request. Some major function codes have associated minor function codes.

`Parameters`

Parameters that are unique for each IRP major function code. This member contains a subset of the Parameters member of the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure.

`Size`

The size, in bytes, of this structure.

`Type`

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the I/O request's type.

## Remarks
The <b>WDF_REQUEST_PARAMETERS</b> structure is used as input to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>. Drivers must call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a> to initialize this structure before they call <b>WdfRequestGetParameters</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>