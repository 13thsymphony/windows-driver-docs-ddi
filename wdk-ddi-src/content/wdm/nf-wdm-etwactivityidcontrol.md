---
UID: NF.wdm.EtwActivityIdControl
title: EtwActivityIdControl function
author: windows-driver-content
description: The EtwActivityIdControl function creates, queries, and sets the current activity identifier.
old-location: devtest\etwactivityidcontrol.htm
old-project: devtest
ms.assetid: dd2e1558-db5d-4d48-a55e-fbdf2838ec55
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: EtwActivityIdControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EtwActivityIdControl
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Comments section
req.product: Windows 10 or later.
---

# EtwActivityIdControl function



## -description
The <b>EtwActivityIdControl</b> function creates, queries, and sets the current activity identifier. 


## -syntax

````
NTSTATUS EtwActivityIdControl(
  _In_    ULONG  ControlCode,
  _Inout_ LPGUID ActivityId
);
````


## -parameters

### -param ControlCode [in]

The <i>ControlCode</i> parameter can be one of the following defined values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param EVENT_ACTIVITY_CTRL_GET_ID

</td>
<td width="60%">
Returns the current thread's activity identifier in the <i>ActivityId</i> parameter.  
</td>
</tr>
<tr>

### -param EVENT_ACTIVITY_CTRL_SET_ID

</td>
<td width="60%">
Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>. Note that the <i>ActivityId</i> you pass to this function
            does not necessarily have to be one created by EVENT_ACTIVITY_CTRL_CREATE_ID or EVENT_ACTIVITY_CTRL_CREATE_SET_ID control code.
            You can use any value that fits inside a GUID, including any available
            local value that would serve your need for
            some type of activity identifier.
</td>
</tr>
<tr>

### -param EVENT_ACTIVITY_CTRL_CREATE_ID

</td>
<td width="60%">
Creates a new identifier and sets the <i>ActivityId</i> parameter to the value of the new identifier.  
</td>
</tr>
<tr>

### -param EVENT_ACTIVITY_CTRL_GET_SET_ID

</td>
<td width="60%">
Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>, and then returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call.  
</td>
</tr>
<tr>

### -param EVENT_ACTIVITY_CTRL_CREATE_SET_ID

</td>
<td width="60%">
Copies the current thread's activity identifier. Creates a new identifier and sets the current thread's   activity identifier to the new value. Returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call. 
</td>
</tr>
</table>
 

### -param ActivityId [in, out]

The identifier that indicates the activity associated with the event. The <i>ActivityId</i> parameter provides a way to group related events and is used in end-to-end tracing.

## -returns
<b>EtwActivityIdControl</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks
Activity identifiers provide a method of linking separate events in a common thread of computation. An <i>activity</i> is a work item performed by an application and or a driver. The concept of activity is a core component in end-to-end tracing.

Callers of <b>EtwActivityIdControl</b> must be running at IRQL &lt; DISPATCH_LEVEL, unless the <i>ControlCode</i> is EVENT_ACTIVITY_CTRL_CREATE_ID, in which case the function can be called at any IRQL.

Use the <a href="devtest.etwactivityidcontrolkernel">EtwActivityIdControlKernel</a> function to  query or set  activity identifiers  kernel threads. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
See Comments section
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="devtest.etwactivityidcontrolkernel">EtwActivityIdControlKernel</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwActivityIdControl function%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
