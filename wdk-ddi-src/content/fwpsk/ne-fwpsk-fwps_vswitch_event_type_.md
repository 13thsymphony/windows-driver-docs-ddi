---
UID : NE:fwpsk.FWPS_VSWITCH_EVENT_TYPE_
title : FWPS_VSWITCH_EVENT_TYPE_
author : windows-driver-content
description : The FWPS_VSWITCH_EVENT_TYPE enumeration type specifies the type of a virtual switch event notification.
old-location : netvista\fwps_vswitch_event_type.htm
old-project : netvista
ms.assetid : 6880bdb1-c889-4f4e-b401-d04b65d9864b
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FWPS_VSWITCH_EVENT_TYPE_, FWPS_VSWITCH_EVENT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FWPS_VSWITCH_EVENT_TYPE
req.alt-loc : fwpsk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---

# FWPS_VSWITCH_EVENT_TYPE_ Enumeration
The FWPS_VSWITCH_EVENT_TYPE enumeration type specifies the type of a virtual switch event notification.

## Syntax
````
typedef enum FWPS_VSWITCH_EVENT_TYPE_ { 
  FWPS_VSWITCH_EVENT_VSWITCH_NONE,
  FWPS_VSWITCH_EVENT_VSWITCH_CREATE,
  FWPS_VSWITCH_EVENT_VSWITCH_DELETE,
  FWPS_VSWITCH_EVENT_PORT_CREATE,
  FWPS_VSWITCH_EVENT_PORT_DELETE,
  FWPS_VSWITCH_EVENT_INTERFACE_CREATE,
  FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT,
  FWPS_VSWITCH_EVENT_INTERFACE_DELETE,
  FWPS_VSWITCH_EVENT_POLICY_ADD,
  FWPS_VSWITCH_EVENT_POLICY_UPDATE,
  FWPS_VSWITCH_EVENT_POLICY_DELETE,
  FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE,
  FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE
} FWPS_VSWITCH_EVENT_TYPE;
````

## Constants

<table>

<tr>
<td>FWPS_VSWITCH_EVENT_INTERFACE_CREATE</td>
<td>Indicates that the virtual switch interface was created.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_INTERFACE_DELETE</td>
<td>Indicates that the virtual switch interface was deleted.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT</td>
<td>Indicates that the virtual switch interface was disconnected.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_POLICY_ADD</td>
<td>Indicates the addition of a policy for a virtual switch port.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_POLICY_DELETE</td>
<td>Indicates the deletion of a policy for a virtual switch port.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_POLICY_UPDATE</td>
<td>Indicates a policy update to a virtual switch port.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_PORT_CREATE</td>
<td>Indicates that the virtual switch port was created.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_PORT_DELETE</td>
<td>Indicates that the virtual switch port was deleted.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE</td>
<td>Indicates a virtual switch run-time state restore event.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE</td>
<td>Indicates a virtual switch run-time state save event.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_VSWITCH_CREATE</td>
<td>Indicates that the virtual switch instance was created.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_VSWITCH_DELETE</td>
<td>Indicates that the virtual switch instance was deleted.</td>
</tr>

<tr>
<td>FWPS_VSWITCH_EVENT_VSWITCH_NONE</td>
<td>Indicates no specific virtual switch event.</td>
</tr>
</table>

## Remarks

The 
    FWPS_VSWITCH_EVENT_TYPE  enumeration defines the values for the <i>eventType</i> parameter of the  virtual switch notification functions that are included in the <a href="..\fwpsk\ns-fwpsk-fwps_vswitch_event_dispatch_table0_.md">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<dl>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_vswitch_event_dispatch_table0_.md">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_EVENT_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>