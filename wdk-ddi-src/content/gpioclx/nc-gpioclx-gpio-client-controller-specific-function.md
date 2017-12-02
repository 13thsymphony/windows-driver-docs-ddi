---
UID: NC.gpioclx.GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION
title: GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION
author: windows-driver-content
description: The CLIENT_ControllerSpecificFunction event callback function performs an operation that is specific to a particular general-purpose I/O (GPIO) controller.
old-location: gpio\client_controllerspecificfunction.htm
old-project: GPIO
ms.assetid: 27551BE5-1260-4F05-9847-97C90ADF7968
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.keywords: PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLIENT_ControllerSpecificFunction
req.alt-loc: Gpioclx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
req.iface: 
---

# GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION callback



## -description
<p>The <i>CLIENT_ControllerSpecificFunction</i> event callback function performs an operation that is specific to a particular general-purpose I/O (GPIO) controller.</p>


## -prototype

````
GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION CLIENT_ControllerSpecificFunction;

NTSTATUS CLIENT_ControllerSpecificFunction(
  _In_    PVOID                                                Context,
  _Inout_ PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS Parameters
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.</p>
</dd>

### -param Parameters [in, out]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698248">GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</a> structure that contains the input and output buffers for the controller-specific operation.</p>
</dd>
</dl>

## -returns
<p>The <i>CLIENT_ControllerSpecificFunction</i> function returns <b>STATUS_SUCCESS</b> if the call is successful. Possible return values include the following error codes.</p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The GPIO controller does not support the operation specified by the input parameters.</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The size of the input buffer or output buffer is too small.</p>

<p> </p>

## -remarks
<p>As an option, a GPIO controller driver can support <a href="https://msdn.microsoft.com/library/windows/hardware/hh698261">IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</a> requests. This type of I/O control request (IOCTL) performs controller-specific operations for the benefit of peripheral device drivers that require these operations. To support this IOCTL, a GPIO controller driver implements a <i>CLIENT_ControllerSpecificFunction</i> function.</p>

<p>The GPIO framework extension (GpioClx) supports the <i>CLIENT_ControllerSpecificFunction</i> function to address the specific needs of certain hardware platforms. Typical GPIO controller drivers do not implement this function. A peripheral device driver that uses <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> requests to perform a hardware-specific operation on one platform risks the loss of compatibility with other platforms that do not support this operation.</p>

<p>Typically, the <i>CLIENT_ControllerSpecificFunction</i> function programs the GPIO controller to perform a hardware-specific operation on a set of GPIO pins. The input and output parameters for this operation are defined by the developer for the GPIO controller driver. Only a peripheral device driver that is aware of the particular operations implemented by a GPIO controller driver can request these operations.</p>

<p>When GpioClx receives an <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> request, it checks to see whether the GPIO controller driver has implemented a <i>CLIENT_ControllerSpecificFunction</i> function. If so, GpioClx copies the descriptions of the input and output buffers from the IOCTL to a <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure and passes a pointer to this structure as a parameter to the <i>CLIENT_ControllerSpecificFunction</i> function. If the parameter values in the <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure are valid, the function performs the requested operation and returns STATUS_SUCCESS.</p>

<p>If GpioClx receives an <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> request, and the GPIO controller driver does not implement a <i>CLIENT_ControllerSpecificFunction</i> function, GpioClx completes the IOCTL with error code STATUS_NOT_IMPLEMENTED.</p>

<p>To define a <i>CLIENT_ControllerSpecificFunction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>CLIENT_ControllerSpecificFunction</i> callback function that is named <code>MyEvtGpioControllerSpecificFunction</code>, use the GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at PASSIVE_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698248">GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698261">IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ControllerSpecificFunction callback function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
