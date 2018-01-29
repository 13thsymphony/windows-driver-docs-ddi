---
UID : NF:fltkernel.FltCreateCommunicationPort
title : FltCreateCommunicationPort function
author : windows-driver-content
description : FltCreateCommunicationPort creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications.
old-location : ifsk\fltcreatecommunicationport.htm
old-project : ifsk
ms.assetid : 9987ed6b-7792-4035-9640-9ee9595e854a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltCreateCommunicationPort function [Installable File System Drivers], FltCreateCommunicationPort, FltApiRef_a_to_d_77aa523f-3374-41e7-9b9f-ed0d9e5b3094.xml, fltkernel/FltCreateCommunicationPort, ifsk.fltcreatecommunicationport
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
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
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltCreateCommunicationPort function
<b>FltCreateCommunicationPort</b> creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications.

## Syntax

````
NTSTATUS FltCreateCommunicationPort(
  _In_     PFLT_FILTER            Filter,
  _Out_    PFLT_PORT              *ServerPort,
  _In_     POBJECT_ATTRIBUTES     ObjectAttributes,
  _In_opt_ PVOID                  ServerPortCookie,
  _In_     PFLT_CONNECT_NOTIFY    ConnectNotifyCallback,
  _In_     PFLT_DISCONNECT_NOTIFY DisconnectNotifyCallback,
  _In_opt_ PFLT_MESSAGE_NOTIFY    MessageNotifyCallback,
  _In_     LONG                   MaxConnections
);
````

## Parameters

`Filter`

Opaque filter pointer for the caller.

`ServerPort`

Pointer to a caller-allocated variable that receives an opaque port handle for the communication server port. The minifilter driver uses this handle to listen for incoming connection requests from a user-mode application.

`ObjectAttributes`

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the attributes of the communication server port. This structure must have been initialized by a previous call to <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>. This parameter is required and cannot be <b>NULL</b>. Members of this structure for a communication port object include the following. 
<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONG </b><b>Length</b>

</td>
<td>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> sets this member to <b>sizeof(</b>OBJECT_ATTRIBUTES<b>)</b>.

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING </b><b>ObjectName</b>

</td>
<td>
Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing a unique name (for example, L"\\MyFilterPort") for the port object. 

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR </b><b>SecurityDescriptor</b>

</td>
<td>
Pointer to a security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>) to be applied to the port object. If needed, a default security descriptor can be created by calling <a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>. 

</td>
</tr>
<tr>
<td>
<b>ULONG </b><b>Attributes</b>

</td>
<td>
Bitmask of flags specifying the desired attributes for the port handle. These flags must include OBJ_KERNEL_HANDLE. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <b>ObjectName</b> rather than performing an exact-match search. 

</td>
</tr>
</table>

`ServerPortCookie`

Pointer to context information defined by the minifilter driver. This information can be used to distinguish among multiple communication server ports that are created by the same minifilter driver. The Filter Manager passes this context pointer as a parameter to the <i>ConnectNotifyCallback</i> routine. This parameter is optional and can be <b>NULL</b>.

`ConnectNotifyCallback`

Pointer to a caller-supplied callback routine. The Filter Manager calls this routine whenever a user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a> to send a connection request to the minifilter driver. This parameter is required and cannot be <b>NULL</b>. This routine is called at IRQL = PASSIVE_LEVEL. 

This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(*PFLT_CONNECT_NOTIFY) (
      IN PFLT_PORT ClientPort,
      IN PVOID ServerPortCookie,
      IN PVOID ConnectionContext,
      IN ULONG SizeOfContext,
      OUT PVOID *ConnectionPortCookie
      );</pre>
</td>
</tr>
</table></span></div>

`DisconnectNotifyCallback`

Pointer to a caller-supplied callback routine to be called whenever the user-mode handle count for the client port reaches zero or when the minifilter driver is about to be unloaded. This parameter is required and cannot be <b>NULL</b>. This routine is called at IRQL = PASSIVE_LEVEL. 

This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_DISCONNECT_NOTIFY) (
      IN PVOID ConnectionCookie
      );</pre>
</td>
</tr>
</table></span></div>

`MessageNotifyCallback`

Pointer to a caller-supplied callback routine. The Filter Manager calls this routine, at IRQL = PASSIVE_LEVEL, whenever a user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a> to send a message to the minifilter driver through the client port. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, any request made from user mode to send data to the port will receive an error. 

This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(*PFLT_MESSAGE_NOTIFY) (
      IN PVOID PortCookie,
      IN PVOID InputBuffer OPTIONAL,
      IN ULONG InputBufferLength,
      OUT PVOID OutputBuffer OPTIONAL,
      IN ULONG OutputBufferLength,
      OUT PULONG ReturnOutputBufferLength
      );</pre>
</td>
</tr>
</table></span></div>

`MaxConnections`

Maximum number of simultaneous client connections to be allowed for this server port. This parameter is required and must be greater than zero.


## Return Value

<b>FltCreateCommunicationPort</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Filter</i> is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltCreateCommunicationPort</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
A minifilter driver communication port with the same name already exists. Port names must be unique. This is an error code. 

</td>
</tr>
</table>

## Remarks

A minifilter driver calls <b>FltCreateCommunicationPort</b> to create a communication server port object. 

After the server port has been created, a user-mode application can connect to the port by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a>. When connected, the user-mode application can send and receive messages by calling user-mode messaging functions such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>. 

Callers must set the OBJ_KERNEL_HANDLE <b>Attributes</b> flag for the <i>ObjectAttributes</i> parameter of <b>FltCreateCommunicationPort</b>. Setting this flag prevents the minifilter driver communication server port handle from being used by a user-mode process in whose context a caller of <b>FltCreateCommunicationPort</b> might be running. If this flag is not set, <b>FltCreateCommunicationPort</b> returns STATUS_INVALID_PARAMETER. 

Any server port that is created by <b>FltCreateCommunicationPort</b> must eventually be closed by calling <a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>. When the server port is closed, no new connections to the server port are allowed, and all calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a> fail. However, any existing connections remain open until they are closed by the user-mode application or the minifilter driver, or until the minifilter driver is unloaded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>

<a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a>

<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>

<a href="..\fltkernel\nf-fltkernel-fltsendmessage.md">FltSendMessage</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>

<a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a>

<a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>

<a href="..\fltkernel\nf-fltkernel-fltcloseclientport.md">FltCloseClientPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>

<a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCreateCommunicationPort function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>