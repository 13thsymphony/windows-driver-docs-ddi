---
UID: NS.ACPIIOCT._ACPI_METHOD_ARGUMENT_V1
title: _ACPI_METHOD_ARGUMENT_V1
author: windows-driver-content
description: The ACPI_METHOD_ARGUMENT structure contains the value of an input or output argument of an ACPI control method.
old-location: acpi\acpi_method_argument.htm
old-project: acpi
ms.assetid: 4038d5a5-9ce7-44cb-a6f0-3033617cfe6a
ms.author: windowsdriverdev
ms.date: 12/2/2017
ms.keywords: _ACPI_METHOD_ARGUMENT_V1, ACPI_METHOD_ARGUMENT, ACPI_METHOD_ARGUMENT_V1
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
req.alt-api: ACPI_METHOD_ARGUMENT_V1
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

# _ACPI_METHOD_ARGUMENT_V1 structure



## -description
The ACPI_METHOD_ARGUMENT structure contains the value of an input or output argument of an ACPI control method.



## -syntax

````
typedef struct _ACPI_METHOD_ARGUMENT_V1 {
  USHORT Type;
  USHORT DataLength;
  union {
    ULONG Argument;
    UCHAR Data[ANYSIZE_ARRAY];
  };
} ACPI_METHOD_ARGUMENT_V1;
````


## -struct-fields

### -field Type

The type of the method argument, as specified by one of the following:




### -field ACPI_METHOD_ARGUMENT_INTEGER

<b>Argument</b> contains an integer value of type ULONG.


### -field ACPI_METHOD_ARGUMENT_STRING

The <b>Data</b> array contains a NULL-terminated ASCII string, and <b>DataLength</b> supplies the number of characters in the string, including the NULL terminator.


### -field ACPI_METHOD_ARGUMENT_BUFFER

The <b>Data</b> array contains custom data, and <b>DataLength</b> supplies the number of consecutive array elements that contain the custom data, beginning with the <b>Data</b>[0] element.


### -field ACPI_METHOD_ARGUMENT_PACKAGE

The <b>Data</b> array contains an ACPI package descriptor and <b>DataLength</b> supplies the number of consecutive array elements that contain the package descriptor, beginning with the <b>Data</b>[0] element. 

</dd>
</dl>

### -field DataLength

The number of UCHAR elements in the <b>Data</b> array that contains the argument data.


### -field Argument

An argument value of type ULONG.


### -field Data

An array of values of type UCHAR that contains argument data.


## -remarks
An ACPI_EVAL_OUTPUT_BUFFER structure includes an <b>Argument</b> array of ACPI_METHOD_ARGUMENT structures. The following IOCTLs evaluate control methods and return output arguments in an <a href="acpi.acpi_eval_output_buffer">ACPI_EVAL_OUTPUT_BUFFER</a> structure:


<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method_ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>


The ACPI_METHOD_ARGUMENT structure is also used to supply an array of complex input arguments to a control method. The <a href="acpi.acpi_eval_input_buffer_complex">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> and <a href="acpi.acpi_eval_input_buffer_complex_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a> structures includes an <b>Argument</b> array of type ACPI_METHOD_ARGUMENT.

For more information about how to use ACPI_METHOD_ARGUMENT structures to supply and retrieve argument data to an ACPI control method, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.


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
<a href="acpi.acpi_eval_input_buffer_complex">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>
</dt>
<dt>
<a href="acpi.acpi_eval_input_buffer_complex_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a>
</dt>
<dt>
<a href="acpi.acpi_eval_output_buffer">ACPI_EVAL_OUTPUT_BUFFER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_METHOD_ARGUMENT_V1 structure%20 RELEASE:%20(12/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

