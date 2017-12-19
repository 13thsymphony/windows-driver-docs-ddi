---
UID: NF.hbaapi.HBA_RegisterForTargetEvents
title: HBA_RegisterForTargetEvents function
author: windows-driver-content
description: The HBA_RegisterForTargetEvents routine registers for target events with a specified target or with all targets associated with an adapter.
old-location: storage\hba_registerfortargetevents.htm
old-project: storage
ms.assetid: a06f6757-e125-4f80-9594-a60fa1fef6e4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: HBA_RegisterForTargetEvents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_RegisterForTargetEvents
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
---

# HBA_RegisterForTargetEvents function



## -description
The <b>HBA_RegisterForTargetEvents</b> routine registers for target events with a specified target or with all targets associated with an adapter. 



## -syntax

````
HBA_STATUS HBA_API HBA_RegisterForTargetEvents(
   HBA_TARGET_CALLBACK callback,
   void                *userData,
   HBA_HANDLE          handle,
   HBA_WWN             hbaPortWWN,
   HBA_WWN             discoveredPortWWN,
   HBA_CALLBACKHANDLE  *callbackHandle,
   HBA_UINT32          allTargets
);
````


## -parameters

### -param callback 

Pointer to a callback routine of type <a href="storage.hba_port_callback">HBA_PORT_CALLBACK</a> that is called when an adapter is added to the system.


### -param userData 

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


### -param handle 

Contains a value returned by the routine <a href="storage.hba_openadapter">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


### -param hbaPortWWN 

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port from which the target was discovered. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param discoveredPortWWN 

Contains a 64-bit WWN that uniquely identifies the remote HBA port from which target events are reported. 


### -param callbackHandle 

Contains an opaque identifier that the user must pass to <a href="storage.hba_removecallback">HBA_RemoveCallback</a> to de-register the callback routine.


### -param allTargets 

Indicates, when nonzero, that the value in <i>discoveredPortWWN</i> will be ignored, and the callback will be called for events associated with all current and future discovered targets. If this member is 0, only events associated with the target specified by <i>discoveredPortWWN</i> will be reported. 


## -returns
The <b>HBA_RegisterForTargetEvents</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RegisterForTargetEvents</b> returns one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the callback registration was successful. 
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>discoveredPortWWN</i>. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the registration of the callback routine. 

 


## -remarks
To stop event delivery, call <b>HBA_RemoveCallback</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hba_openadapter">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="storage.hba_port_callback">HBA_PORT_CALLBACK</a>
</dt>
<dt>
<a href="storage.hba_removecallback">HBA_RemoveCallback</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RegisterForTargetEvents routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

