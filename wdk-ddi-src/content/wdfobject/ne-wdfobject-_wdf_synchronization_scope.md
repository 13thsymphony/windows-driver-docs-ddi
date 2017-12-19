---
UID: NE.wdfobject._WDF_SYNCHRONIZATION_SCOPE
title: _WDF_SYNCHRONIZATION_SCOPE
author: windows-driver-content
description: The WDF_SYNCHRONIZATION_SCOPE enumeration type specifies how the framework will synchronize execution of an object's event callback functions.
old-location: wdf\wdf_synchronization_scope.htm
old-project: wdf
ms.assetid: a251bf5c-c09b-4097-a9ed-82f2312ac408
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_SYNCHRONIZATION_SCOPE, WDF_SYNCHRONIZATION_SCOPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_SYNCHRONIZATION_SCOPE
req.alt-loc: wdfobject.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# _WDF_SYNCHRONIZATION_SCOPE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_SYNCHRONIZATION_SCOPE enumeration type specifies how the framework will synchronize execution of an object's event callback functions.



## -syntax

````
typedef enum _WDF_SYNCHRONIZATION_SCOPE { 
  WdfSynchronizationScopeInvalid            = 0x00,
  WdfSynchronizationScopeInheritFromParent  = 0x1,
  WdfSynchronizationScopeDevice             = 0x2,
  WdfSynchronizationScopeQueue              = 0x3,
  WdfSynchronizationScopeNone               = 0x4
} WDF_SYNCHRONIZATION_SCOPE;
````


## -enum-fields

### -field WdfSynchronizationScopeInvalid

Reserved for system use.


### -field WdfSynchronizationScopeInheritFromParent

The framework uses the synchronization scope value that was specified for the object's parent object. This value is the default if a driver does not specify a WDF_SYNCHRONIZATION_SCOPE-typed value.


### -field WdfSynchronizationScopeDevice

The framework synchronizes execution of the event callback functions of all queue and file objects that are underneath a device object in the driver's object hierarchy. 

Additionally, if the driver sets the <b>AutomaticSerialization</b> member to <b>TRUE</b> in the configuration structure for an interrupt, DPC, work-item, or timer object that is underneath the same device object, the framework also synchronizes that object's callback functions. 

The framework obtains the device object's synchronization lock before calling a callback function. Therefore, these callback functions run one at a time. However, if the driver creates multiple objects of the same type, but under different device objects, their event callback functions might run concurrently on a multiprocessor system.


### -field WdfSynchronizationScopeQueue

This value affects queue objects only. The framework synchronizes the event callback functions of the queue object so that only one executes at a time. 

Additionally, if the driver sets <b>AutomaticSerialization</b> to <b>TRUE</b> in the configuration structure for an interrupt, DPC, work-item, or timer object that is underneath the queue object or its parent device object, the framework also synchronizes that object's callback functions. 

The framework obtains the queue object's synchronization lock before calling any callback functions that belong to the object. 

If the driver creates multiple queue objects, their event callback functions might run concurrently on a multiprocessor system.

For framework versions 1.9 and later, a driver should set <b>WdfSynchronizationScopeQueue</b> for individual queue objects. To use this scope with earlier versions of the framework, the driver must set <b>WdfSynchronizationScopeQueue</b> for the parent device object and <b>WdfSynchronizationScopeInheritFromParent</b> for the queue object.


### -field WdfSynchronizationScopeNone

The framework does not synchronize the object's event callback functions, so the callback functions might run concurrently on a multiprocessor system.


## -remarks
Drivers use the WDF_SYNCHRONIZATION_SCOPE enumeration type to specify the <b>SynchronizationScope</b> member of an object's <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.

You can specify a <b>SynchronizationScope</b> value for only the following objects:

Framework driver objects

Framework device objects

Framework queue objects

The framework sets the <b>SynchronizationScope</b> value of framework driver objects to <b>WdfSynchronizationScopeNone</b>. It sets the <b>SynchronizationScope</b> value of framework device objects and framework queue objects to <b>WdfSynchronizationScopeInheritFromParent</b>.

For more information about synchronization of a driver's event callback functions, see <a href="wdf.synchronization_techniques_for_wdf_drivers">Synchronization Techniques for Framework-Based Drivers</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfobject.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_SYNCHRONIZATION_SCOPE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

