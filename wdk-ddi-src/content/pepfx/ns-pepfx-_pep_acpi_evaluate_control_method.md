---
UID: NS:pepfx._PEP_ACPI_EVALUATE_CONTROL_METHOD
title: _PEP_ACPI_EVALUATE_CONTROL_METHOD
author: windows-driver-content
description: The PEP_ACPI_EVALUATE_CONTROL_METHOD structure specifies an ACPI control method to evaluate, an input argument to supply to this method, and an output buffer for the result of the evaluation.
old-location: kernel\pep_acpi_evaluate_control_method.htm
old-project: kernel
ms.assetid: FFCC5947-1DD5-4AD5-A414-94BDC013D1A7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_ACPI_EVALUATE_CONTROL_METHOD, PEP_ACPI_EVALUATE_CONTROL_METHOD, *PPEP_ACPI_EVALUATE_CONTROL_METHOD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_EVALUATE_CONTROL_METHOD
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PEP_ACPI_EVALUATE_CONTROL_METHOD, *PPEP_ACPI_EVALUATE_CONTROL_METHOD
---

# _PEP_ACPI_EVALUATE_CONTROL_METHOD structure



## -description
The <b>PEP_ACPI_EVALUATE_CONTROL_METHOD</b> structure specifies an ACPI control method to evaluate, an input argument to supply to this method, and an output buffer for the result of the evaluation.



## -syntax

````
typedef struct _PEP_ACPI_EVALUATE_CONTROL_METHOD {
  PEPHANDLE             DeviceHandle;
  ULONG                 RequestFlags;
  union {
    ULONG       MethodNameUlong;
    ANSI_STRING MethodNameString;
  };
  NTSTATUS              MethodStatus;
  PVOID                 CompletionContext;
  ULONG                 InputArgumentCount;
  SIZE_T                InputArgumentSize;
  PACPI_METHOD_ARGUMENT InputArguments;
  ULONG                 OutputArgumentCount;
  SIZE_T                OutputArgumentSize;
  PACPI_METHOD_ARGUMENT OutputArguments;
} PEP_ACPI_EVALUATE_CONTROL_METHOD, *PPEP_ACPI_EVALUATE_CONTROL_METHOD;
````


## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="kernel.pep_notify_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field RequestFlags

[in] A set of flags. This member contains one of the following values.

<table>
<tr>
<th>Flag name</th>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>PEP_ACPI_ECM_FLAG_NONE</td>
<td>0x0</td>
<td>Not a valid control method name.</td>
</tr>
<tr>
<td>PEP_ACPI_ECM_FLAG_RELATIVE_NAME</td>
<td>0x1</td>
<td>The <b>MethodNameUlong</b> member contains a path-relative control method name.</td>
</tr>
<tr>
<td>PEP_ACPI_ECM_FLAG_FULLY_QUALIFIED_NAME</td>
<td>0x2</td>
<td>The <b>MethodNameString</b> member contains a fully qualified control method name.</td>
</tr>
</table>
 


### -field ( unnamed union )

A union that contains either the four-character path-relative control method name (if <b>RequestFlags</b> = PEP_ACPI_ECM_FLAG_RELATIVE_NAME) or the fully qualified control method name (if <b>RequestFlags</b> = PEP_ACPI_ECM_FLAG_FULLY_QUALIFIED_NAME).


### -field MethodNameUlong

[in] A ULONG value that contains the four-character, path-relative name of the ACPI control method.


### -field MethodNameString

[in] An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure that contains the fully qualified name of the ACPI control method. This name specifies the the path and name of the method in the ACPI namespace. For more information, see <a href="https://msdn.microsoft.com/fe0553df-a5b9-46c4-8e1d-8b89a7d4ad67">Enumerating Child Devices and Control Methods</a>.

</dd>
</dl>

### -field MethodStatus

[out] An NTSTATUS value that indicates the status of the evaluation of the ACPI control method. Set this member to STATUS_SUCCESS to indicate that the platform extension plug-in (PEP) successfully completed its evaluation of the method. Set to STATUS_NOT_SUPPORTED to indicate that the PEP does not recognize the control method. Set to STATUS_BUFFER_TOO_SMALL to indicate that the output buffer size specified by the <b>InputArgumentSize</b> member is not large enough to contain the method results.

If the PEP is to evaluate the method asychronously, set this member to STATUS_PENDING and return from the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186625">AcceptAcpiNotification</a> callback. Later, when the evaluation is completed, the PEP calls the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a> routine to notify the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) that the evaluation of the control method is complete.


### -field CompletionContext

[in] A pointer to a completion context value. The PEP uses this member only if the control method is evaluated asynchronously. In this case, the PEP supplies this completion context pointer in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a> routine that notifies the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) that the evaluation of the control method is complete. Included in the input parameters to this call is a pointer to a <a href="..\pepfx\ns-pepfx-_pep_work_acpi_evaluate_control_method_complete.md">PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</a> structure to which the PEP has written the completion context pointer. The context is opaque to the PEP and contains data used internally by PoFx.


### -field InputArgumentCount

[in] The number of input arguments in the input buffer pointed to by the <b>InputArguments</b> member. Each argument starts with an <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structure that specifies the size of the argument. Currently, the maximum <b>InputArgumentCount</b> value is one.


### -field InputArgumentSize

[in] The size, in bytes, of the input buffer pointed to by the <b>InputArguments</b> member.


### -field InputArguments

[in] A pointer to an input buffer that contains an <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structure that specifies the input argument for the specified ACPI control method.


### -field OutputArgumentCount

[in] The number of output arguments in the output buffer pointed to by the <b>OutputArguments</b> member. Each argument starts with an <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structure that specifies the size of the argument. Currently, the maximum allowed <b>OutputArgumentCount</b> value is one.


### -field OutputArgumentSize

[in, out] On input, the size, in bytes, of the output buffer pointed to by the <b>OutputArguments</b> member. If this buffer is not large enough to contain the result of evaluating the method, the PEP overwrites the <b>OutputArgumentSize</b> input value with the required size, and sets the <b>MethodStatus</b> member to STATUS_BUFFER_TOO_SMALL.


### -field OutputArguments

[in] A pointer to an output buffer to which the PEP writes an <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structure that contains the result of evaluating the specified ACPI control method.


## -remarks
This structure is used by the <a href="kernel.pep_notify_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification. The <b>MethodStatus</b> member contains an output value that the PEP writes to the structure in response to this notification. The <b>OutputArgumentSize</b> member contains an input value supplied by PoFx when the notification is sent. The PEP may overwrite this input value with an output value if the input value is less than the required output buffer size. All other members of this structure contain input values that are supplied by PoFx when the notification is sent.


## -see-also
<dl>
<dt>
<a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
<dt>
<a href="kernel.pep_notify_acpi_evaluate_control_method">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a>
</dt>
<dt>
<a href="kernel.pep_notify_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_EVALUATE_CONTROL_METHOD structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

