---
UID : NC:wsk.PFN_WSK_CONTROL_SOCKET
title : PFN_WSK_CONTROL_SOCKET
author : windows-driver-content
description : The WskControlSocket function performs control operations on a socket.
old-location : netvista\wskcontrolsocket.htm
old-project : netvista
ms.assetid : d65fd2ab-ffca-4e13-b0f1-42d6a89f4b4a
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wskcontrolsocket, WskControlSocket callback function [Network Drivers Starting with Windows Vista], WskControlSocket, PFN_WSK_CONTROL_SOCKET, PFN_WSK_CONTROL_SOCKET, wsk/WskControlSocket, wskref_03c8029d-c31f-4010-9e56-e4c1f91930c5.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
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
req.irql : "<= DISPATCH_LEVEL (see Remarks section)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WNODE_HEADER, *PWNODE_HEADER
req.product : Windows 10 or later.
---


# PFN_WSK_CONTROL_SOCKET callback function
The 
  <b>WskControlSocket</b> function performs control operations on a socket.

## Syntax

```
PFN_WSK_CONTROL_SOCKET PfnWskControlSocket;

NTSTATUS PfnWskControlSocket(
  PWSK_SOCKET Socket,
  WSK_CONTROL_SOCKET_TYPE RequestType,
  ULONG ControlCode,
  ULONG Level,
  SIZE_T InputSize,
  PVOID InputBuffer,
  SIZE_T OutputSize,
  PVOID OutputBuffer,
  SIZE_T *OutputSizeReturned,
  PIRP Irp
)
{...}
```

## Parameters

`Socket`

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket on which the control operation is being performed.

`RequestType`

A value that specifies the type of control operation that is being performed. A WSK application
     sets this parameter to one of the following values:

`ControlCode`

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskSetOption</b> or 
     <b>WskGetOption</b>, the 
     <i>ControlCode</i> parameter specifies the particular socket option whose value is being set or
     retrieved. For more information about socket options that are supported by the WSK subsystem, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>. The underlying
     network protocol might support additional socket options.
     

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>ControlCode</i> parameter specifies the particular I/O control operation that is being performed. For
     more information about I/O control operations that are supported by the WSK subsystem, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a>. The
     underlying network protocol might support additional socket I/O control operations.

`Level`

The level in the network stack at which the value for a socket option is being either set or
     retrieved. For WSK subsystem level socket options, the WSK application should set this parameter to
     SOL_SOCKET. For transport protocol or network protocol level socket options, the WSK application should
     set this parameter to the appropriate level for the underlying transport.
     

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>Level</i> parameter is ignored.

`InputSize`

The number of bytes of data in the buffer that is pointed to by the 
     <i>InputBuffer</i> parameter.

`InputBuffer`

A caller-allocated buffer that supplies any input data that is required to perform the specified
     control operation. If no input data is required for the specified control operation, the WSK application
     should set this parameter to <b>NULL</b> and set the 
     <i>InputSize</i> parameter to zero.

`OutputSize`

The size of the buffer that is pointed to by the 
     <i>OutputBuffer</i> parameter.

`OutputBuffer`

A caller-allocated buffer that receives any output data that is returned by the specified control
     operation. If no output data is returned by the specified control operation, the WSK application should
     set this parameter to <b>NULL</b> and set the 
     <i>OutputSize</i> parameter to zero.

`*OutputSizeReturned`



`Irp`

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the control operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <mshelp:link keywords="netvista.using_irps_with_winsock_kernel_functions" tabindex="0">Using IRPs with Winsock
     Kernel Functions</mshelp:link>.
     

If the 
     <i>RequestType</i> parameter is set to either 
     <b>WskSetOption</b> or 
     <b>WskGetOption</b>, the 
     <i>Irp</i> parameter is required, is optional, or must be <b>NULL</b> depending on the particular socket option
     that is being set or retrieved. For more information about the requirements for the 
     <i>Irp</i> parameter for each of the supported socket options, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>.

If the 
     <i>RequestType</i> parameter is set to 
     <b>WskIoctl</b>, the 
     <i>Irp</i> parameter is required, is optional, or must be <b>NULL</b> depending on the particular I/O control
     operation that is being performed. For more information about the requirements for the 
     <i>Irp</i> parameter for each of the supported I/O control operations, see 
     <mshelp:link keywords="netvista.wsk_socket_ioctl_operations" tabindex="0">WSK Socket IOCTL
     Operations</mshelp:link>.


## Return Value

<b>WskControlSocket</b> returns one of the following NTSTATUS codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The control operation completed successfully. If the WSK application specified a pointer to an
       IRP in the 
       <i>Irp</i> parameter, the IRP will be completed with success status, and the number of bytes that is
       returned in the buffer that is pointed to by the 
       <i>OutputBuffer</i> parameter will be returned in the 
       <b>IoStatus.Information</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not complete the control operation immediately. The WSK subsystem will
       complete the IRP after it has completed the control operation. The status of the control operation
       will be returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the number of bytes that is
       returned in the buffer that is pointed to by the 
       <i>OutputBuffer</i> parameter will be returned in the 
       <b>IoStatus.Information</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EVENT_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not complete the control operation immediately. This value is returned
       only when a WSK application is disabling an event callback function on a socket when there are
       currently in-progress calls to that event callback function and when the 
       <i>Irp</i> parameter is <b>NULL</b>. For more information about disabling event callback functions, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>

## Remarks

If a WSK application specifies 
    <b>WskSetOption</b> or 
    <b>WskGetOption</b> in the 
    <i>RequestType</i> parameter, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a> for more information
    about how the input and output buffers are used for each socket option.

If a WSK application specifies 
    <b>WskIoctl</b> in the 
    <i>RequestType</i> parameter, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a> for
    more information about how the input and output buffers are used for each I/O control operation.

If the 
    <b>WskControlSocket</b> function returns STATUS_PENDING, any buffers that are pointed to by the 
    <i>InputBuffer</i> parameter or the 
    <i>OutputBuffer</i> parameter must remain valid until the IRP is completed. If the WSK application
    allocated the buffers with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffers on the
    stack, it cannot return from the function that calls the 
    <b>WskControlSocket</b> function until after the IRP is completed.

Callers of the 
    <b>WskControlSocket</b> function must be running at IRQL &lt;= DISPATCH_LEVEL except when the 
    <i>RequestType</i> parameter is set to 
    <b>WskIoctl</b> and the 
    <i>ControlCode</i> parameter is set to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570815">SIO_ADDRESS_LIST_QUERY</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570814">SIO_ADDRESS_LIST_CHANGE</a>, or <a href="https://msdn.microsoft.com/bf380ddf-8171-4ef4-be47-94c7a6aabf0a">SIO_ADDRESS_LIST_SORT</a>. In this
    situation, callers must be running at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL (see Remarks section) |
| **DDI compliance rules** |  |

## See Also

<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>

<mshelp:link keywords="netvista.wsk_provider_connection_dispatch" tabindex="0"><b>
   WSK_PROVIDER_CONNECTION_DISPATCH</b></mshelp:link>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<mshelp:link keywords="netvista.wsk_provider_datagram_dispatch" tabindex="0"><b>
   WSK_PROVIDER_DATAGRAM_DISPATCH</b></mshelp:link>

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>

<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wsk-socket-ioctl-operations">WSK Socket IOCTL Operations</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571186">WSK Socket Options</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CONTROL_SOCKET callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>