---
UID: NE:ntddk._PSCREATETHREADNOTIFYTYPE
title: _PSCREATETHREADNOTIFYTYPE
author: windows-driver-content
description: Indicates the type of thread notification. This enumeration is used in PsSetCreateThreadNotifyRoutineEx to register callback notifications associated with thread creation or deletion.
old-location: kernel\pscreatethreadnotifytype.htm
old-project: kernel
ms.assetid: C38F8222-7F22-4D6B-A3F2-C326ECE22E8B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PSCREATETHREADNOTIFYTYPE, PSCREATETHREADNOTIFYTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PSCREATETHREADNOTIFYTYPE
req.alt-loc: Ntddk.h
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
req.typenames: PSCREATETHREADNOTIFYTYPE
---

# _PSCREATETHREADNOTIFYTYPE enumeration



## -description
Indicates the type of thread notification. This enumeration is used in <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a> to register callback notifications associated with thread creation or deletion.



## -syntax

````
typedef enum _PSCREATETHREADNOTIFYTYPE { 
  PsCreateThreadNotifyNonSystem   = 0,
  PsCreateThreadNotifySubsystems  = 1
} PSCREATETHREADNOTIFYTYPE;
````


## -enum-fields

### -field PsCreateThreadNotifyNonSystem

The driver-registered callback function is executed on the new non-system thread, which enables the callback function to perform tasks such as setting the initial thread context.



### -field PsCreateThreadNotifySubsystems

Indicates that the driver-registered callback function is invoked for threads of all subsystems.  Drivers can call <a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a> to determine the underlying subsystem. The query retrieves a  <a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a> value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1703

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PSCREATETHREADNOTIFYTYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

