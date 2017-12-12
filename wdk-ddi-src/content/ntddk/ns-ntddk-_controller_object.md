---
UID: NS.NTDDK._CONTROLLER_OBJECT
title: _CONTROLLER_OBJECT
author: windows-driver-content
description: A controller object represents a hardware adapter or controller with homogenous devices that are the actual targets for I/O requests.
old-location: kernel\controller_object.htm
old-project: kernel
ms.assetid: a5530901-e48c-4f4e-86a8-00d5ed01f933
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _CONTROLLER_OBJECT, *PCONTROLLER_OBJECT, CONTROLLER_OBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CONTROLLER_OBJECT
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
req.irql: PASSIVE_LEVEL
---

# _CONTROLLER_OBJECT structure



## -description
A controller object represents a hardware adapter or controller with homogenous devices that are the actual targets for I/O requests. A controller object can be used to synchronize a device driver's I/O to the target devices through its hardware adapter/controller. 

A controller object is partially opaque. Driver writers must know about a certain field associated with the controller object because their drivers access this field through the controller object pointer returned by <b>IoCreateController</b>. The following field in a controller object is accessible to the creating driver. 



## -syntax

````
typedef struct _CONTROLLER_OBJECT {
  PVOID ControllerExtension;
} CONTROLLER_OBJECT, *PCONTROLLER_OBJECT;
````


## -struct-fields

### -field ControllerExtension

Pointer to the controller extension. The structure and contents of the controller extension are driver-defined. The size is driver-determined, specified in the driver's call to <b>IoCreateController</b>. Usually, drivers maintain common state about I/O operations in the controller extension and device-specific state about I/O for a target device in the corresponding device extension. 


## -remarks
Most driver routines that process IRPs are given a pointer to the target device object. Consequently, device drivers that use controller objects frequently store the controller object pointer returned by <b>IoCreateController</b> in each device extension. 

Note that a controller object has no name so it cannot be the target of an I/O request, and higher-level drivers cannot connect or attach their device objects to a device driver's controller object. 

Undocumented fields within a controller object should be considered inaccessible. Drivers with dependencies on object field locations or access to undocumented fields might not remain portable and interoperable with other drivers over time.


## -requirements
<table>
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
<a href="kernel.iocreatecontroller">IoCreateController</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CONTROLLER_OBJECT structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

