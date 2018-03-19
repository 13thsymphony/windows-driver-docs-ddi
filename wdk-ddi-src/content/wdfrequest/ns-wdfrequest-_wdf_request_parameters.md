---
UID: NS:wdfrequest._WDF_REQUEST_PARAMETERS
title: "_WDF_REQUEST_PARAMETERS"
author: windows-driver-content
description: The WDF_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O request.
old-location: wdf\wdf_request_parameters.htm
old-project: wdf
ms.assetid: 012e34c0-3cc6-49dc-94ad-d359d857720f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_REQUEST_PARAMETERS, DFRequestObjectRef_b3f1759e-7bdd-4222-8aea-502bd45e16bf.xml, PWDF_REQUEST_PARAMETERS, PWDF_REQUEST_PARAMETERS structure pointer, WDF_REQUEST_PARAMETERS, WDF_REQUEST_PARAMETERS structure, _WDF_REQUEST_PARAMETERS, kmdf.wdf_request_parameters, wdf.wdf_request_parameters, wdfrequest/PWDF_REQUEST_PARAMETERS, wdfrequest/WDF_REQUEST_PARAMETERS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
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


`Size`

The size, in bytes, of this structure.

`MinorFunction`

The IRP minor function code, if any, that is associated with the I/O request. Some major function codes have associated minor function codes.

`Type`

A <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the I/O request's type.

`Parameters`

Parameters that are unique for each IRP major function code. This member contains a subset of the Parameters member of the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure.

## Remarks
The <b>WDF_REQUEST_PARAMETERS</b> structure is used as input to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>. Drivers must call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a> to initialize this structure before they call <b>WdfRequestGetParameters</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a>