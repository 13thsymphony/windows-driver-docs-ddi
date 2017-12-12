---
UID: NS.ACPIIOCT._ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1~R1
title: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1
author: windows-driver-content
description: The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input argument that is an ASCII string.
old-location: acpi\acpi_eval_input_buffer_simple_string.htm
old-project: acpi
ms.assetid: f8f5db79-d1ea-4ce8-b941-49ef7518b941
ms.author: windowsdriverdev
ms.date: 12/2/2017
ms.keywords: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1
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
req.alt-api: ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1
req.alt-loc: Acpiioct.h
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
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1 structure



## -description
The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method and an input argument that is an ASCII string. 



## -syntax

````
typedef struct _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1 {
  ULONG Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  };
  ULONG StringLength;
  UCHAR String[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1;
````


## -struct-fields

### -field Signature

The signature of a string input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_SIGNATURE.


### -field MethodName

This union member is a four-element ASCII character array that contains the name of the method. For example, 'ABCD.'


### -field MethodNameAsUlong

This union member is a ULONG-typed variable that contains the name of the method in the format (ULONG) ('DCBA'), where the method name is the four-element ASCII character array 'ABCD.'


### -field StringLength

The number of ASCII characters in the array of characters that is supplied by <b>String</b>.


### -field String

An ASCII character string that contains the number of characters that is specified by <b>StringLength</b>. The string does not include a NULL terminator. 


## -remarks
If a device supports a control method named ABCD that takes an ASCII string as input, a driver for the device can evaluate the method by sending an IOCTL_ACPI_EVAL_METHOD request or an IOCTL_ACPI_ASYNC_EVAL_METHOD request to the device and setting the members of the input ACPI_EVAL_INPUT_BUFFER structure as follows:

Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_SIGNATURE.

Set <b>MethodName</b> to 'ABCD' or <b>MethodNameAsUlong</b> to (ULONG)('DCBA').

Set <b>StringLength</b> to the number of characters that is supplied by <b>String</b>.

Set <b>String</b> to the input string.

For more information about how to use this structure, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>
</dt>
<dt>
<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1 structure%20 RELEASE:%20(12/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

