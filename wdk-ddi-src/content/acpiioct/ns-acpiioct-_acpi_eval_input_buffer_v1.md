---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_V1
title: "_ACPI_EVAL_INPUT_BUFFER_V1"
author: windows-driver-content
description: The ACPI_EVAL_INPUT_BUFFER structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method that does not take an input argument.
old-location: acpi\acpi_eval_input_buffer.htm
old-project: acpi
ms.assetid: a911fab9-516f-4ac5-ae33-1b6e218f9349
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER, *PACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER, ACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER_V1 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_V1, PACPI_EVAL_INPUT_BUFFER_V1 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_V1, acpi-meth-eval-ref_fda162bd-f908-46bf-a5a9-66daeb6b6aaf.xml, acpi.acpi_eval_input_buffer, acpiioct/ACPI_EVAL_INPUT_BUFFER_V1, acpiioct/PACPI_EVAL_INPUT_BUFFER_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 and later versions of Windows.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Acpiioct.h
api_name:
-	ACPI_EVAL_INPUT_BUFFER_V1
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_V1, *PACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER, *PACPI_EVAL_INPUT_BUFFER
---

# _ACPI_EVAL_INPUT_BUFFER_V1 structure
The ACPI_EVAL_INPUT_BUFFER structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method that does not take an input argument.

## Syntax
````
typedef struct _ACPI_EVAL_INPUT_BUFFER_V1 {
  ULONG Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
} ACPI_EVAL_INPUT_BUFFER_V1, *PACPI_EVAL_INPUT_BUFFER_V1;
````

## Members


`DUMMYUNIONNAME`

#### MethodName

A four-element ASCII character array that contains the name of a control method, for example, 'ABCD.' 



#### MethodNameAsUlong

A value of type ULONG that contains the name of the method in the format (ULONG) ('DCBA'), where the method name is the four-element ASCII character array 'ABCD.'

`Signature`

The signature of an input buffer that does not include an argument, which must be set to ACPI_EVAL_INPUT_BUFFER_SIGNATURE.

## Remarks
If a device supports a control method named 'ABCD' that does not take an input argument, a driver for the device can evaluate the method by sending an IOCTL_ACPI_EVAL_METHOD request or an IOCTL_ACPI_ASYNC_EVAL_METHOD request to the device and setting the members of the input ACPI_EVAL_INPUT_BUFFER structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIGNATURE.

</li>
<li>
Set <b>MethodName</b> to 'ABCD' or <b>MethodNameAsUlong</b> to (ULONG)('DCBA').

</li>
</ul>
For more information about how to use this structure, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 2000 and later versions of Windows. Windows 2000 and later versions of Windows. |
| **Header** | acpiioct.h (include Acpiioct.h) |

## See Also

<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_INPUT_BUFFER_V1 structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>