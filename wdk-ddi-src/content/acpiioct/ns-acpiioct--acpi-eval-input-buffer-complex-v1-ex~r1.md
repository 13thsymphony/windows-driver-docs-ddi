---
UID: NS.acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX~r1
title: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
author: windows-driver-content
description: The ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request.
old-location: acpi\acpi_eval_input_buffer_complex_ex.htm
old-project: acpi
ms.assetid: 6053f535-da9c-4f9d-885f-01f29cabd9ee
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
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

# ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure



## -description
<p>The ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl-acpi-eval-method-ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a> request and to an <a href="..\acpiioct\ni-acpiioct-ioctl-acpi-async-eval-method-ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a> request. The structure supplies the path and name of a control method in an ACPI namespace and an input argument array of <a href="acpi.acpi_method_argument">ACPI_METHOD_ARGUMENT</a> structures. </p>


## -syntax

````
typedef struct _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX {
  ULONG                Signature;
  CHAR                 MethodName[256];
  ULONG                Size;
  ULONG                ArgumentCount;
  ACPI_METHOD_ARGUMENT Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX;
````


## -struct-fields
<dl>

### -field Signature

<dd>
<p>The signature of an extended complex input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE_EX. </p>
</dd>

### -field MethodName

<dd>
<p>A NULL-terminated ASCII string that contains the path and name of a control method in an ACPI namespace. The maximum number of characters that the string can contain, including a NULL terminator, is 256. </p>
<p>For more information about how to supply the path and name of a control method, see the Remarks section later in this topic.</p>
</dd>

### -field Size

<dd>
<p>The number of bytes that the <b>Argument</b> array contains.</p>
</dd>

### -field ArgumentCount

<dd>
<p>The number of variable-length ACPI_METHOD_ARGUMENT structures that the <b>Argument</b> array contains. The <b>Argument</b> array can hold a maximum of seven argument structures.</p>
</dd>

### -field Argument

<dd>
<p>An array of ACPI_METHOD_ARGUMENT structures.</p>
</dd>
</dl>

## -remarks
<p>A driver for a device can use an IOCTL_ACPI_EVAL_METHOD_EX request or an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request to evaluate a control method that is a descendant child object of the device. If the method takes a complex array of arguments, these requests take an input ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure as follows:</p>

<p>Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE_EX.</p>

<p>Set <b>MethodName</b> to a NULL-terminated string that supplies either the full path and name to a control method in the ACPI namespace or the path and name of the method relative to the device to which the evaluation request is sent. </p>

<p>For example, assume that a request is sent to a device named 'ABCD,' which is an immediate child of the root of an ACPI namespace, that 'ABCD' device supports a child device named 'CHLD,' and that the 'CHLD' device supports a method named '_FOO.' In this case, the evaluation request can supply either '\ABCD.CHLD._FOO,' which is the fully qualified path and name of the control method in the ACPI namespace, or 'CHLD._FOO,' which is the path and name of the control method that is relative to the 'ABCD' device in the ACPI namespace. </p>

<p>For more information about how to obtain the fully qualified path and name of a control method in an ACPI namespace, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p><b>Size</b> is set to the number of bytes in the <b>Argument</b> array. </p>

<p><b>ArgumentCount</b> is set to the number of arguments in the <b>Argument</b> array.</p>

<p><b>Argument</b> is set to an array of ACPI_METHOD_ARGUMENT structures.</p>

<p>For more information about how to use this structure, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows Vista and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="acpi.acpi_method_argument">ACPI_METHOD_ARGUMENT</a>
</dt>
<dt>
<a href="..\acpiioct\ni-acpiioct-ioctl-acpi-async-eval-method-ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>
</dt>
<dt>
<a href="..\acpiioct\ni-acpiioct-ioctl-acpi-eval-method-ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
