---
UID : NC:wdfwmi.EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
title : EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
author : windows-driver-content
description : A driver's EvtWmiInstanceExecuteMethod callback function executes a specified method that the driver provides for a WMI data provider's instance.
old-location : wdf\evtwmiinstanceexecutemethod.htm
old-project : wdf
ms.assetid : b14de1d7-0df2-46d1-a3bd-c23f33d3ed75
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtwmiinstanceexecutemethod, EvtWmiInstanceExecuteMethod callback function, EvtWmiInstanceExecuteMethod, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD, wdfwmi/EvtWmiInstanceExecuteMethod, DFWMIRef_d54dc0b0-bdef-40a7-b863-5946f4d8e5f5.xml, kmdf.evtwmiinstanceexecutemethod
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfwmi.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS"
req.product : Windows 10 or later.
---


# EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD function
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtWmiInstanceExecuteMethod</i> callback function executes a specified method that the driver provides for a WMI data provider's instance.

## Syntax

```
EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD EvtWdfWmiInstanceExecuteMethod;

NTSTATUS EvtWdfWmiInstanceExecuteMethod(
  WDFWMIINSTANCE WmiInstance,
  ULONG MethodId,
  ULONG InBufferSize,
  ULONG OutBufferSize,
  PVOID Buffer,
  PULONG BufferUsed
)
{...}
```

## Parameters

`WmiInstance`

A handle to a WMI instance object.

`MethodId`

A value that identifies a method in a provider instance. This value corresponds to the <a href="https://msdn.microsoft.com/e2d281b3-913c-43ad-921c-80dc8be09aa0">WmiMethodId</a> value that is specified in the provider's MOF file.

`InBufferSize`

The number of bytes of input data.

`OutBufferSize`

The number of bytes of output data that the buffer that <i>Buffer</i> points to can hold.

`Buffer`

A pointer to a buffer that is used for input, output, or both, as determined by the specified method. If both input and output data are provided, the driver overwrites the input data with the output data.

`BufferUsed`

A pointer to a location that receives the number of bytes that the driver wrote into the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.


## Return Value

The <i>EvtWmiInstanceExecuteMethod</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. The driver must return STATUS_BUFFER_TOO_SMALL if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data.

## Remarks

To register an <i>EvtWmiInstanceExecuteMethod</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>. 

After a driver executes the instance method that the <i>MethodId</i> parameter specifies, the driver must use the <i>BufferUsed</i> parameter to store the number of bytes that were written to the buffer.

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceExecuteMethod</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceExecuteMethod</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfwmi.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_instance.md">EvtWmiInstanceSetInstance</a>

<a href="..\wdfwmi\ns-wdfwmi-_wdf_wmi_instance_config.md">WDF_WMI_INSTANCE_CONFIG</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_query_instance.md">EvtWmiInstanceQueryInstance</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>

<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_instance_set_item.md">EvtWmiInstanceSetItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>