---
UID: NF:wdfobject.WdfObjectAllocateContext
title: WdfObjectAllocateContext function
author: windows-driver-content
description: The WdfObjectAllocateContext method allocates context space for a specified framework object.
old-location: wdf\wdfobjectallocatecontext.htm
old-project: wdf
ms.assetid: dbabd045-4f18-4103-b3c0-5405173628d6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfObjectAllocateContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfObjectAllocateContext
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectAllocateContext function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectAllocateContext</b> method allocates context space for a specified framework object.



## -syntax

````
NTSTATUS WdfObjectAllocateContext(
  _In_  WDFOBJECT              Handle,
  _In_  PWDF_OBJECT_ATTRIBUTES ContextAttributes,
  _Out_ PVOID                  *Context
);
````


## -parameters

### -param Handle [in]

A handle to a framework object.


### -param ContextAttributes [in]

A pointer to a caller-supplied <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes the context space.


### -param Context [out]

A pointer to a location that receives a pointer to the allocated context space.


## -returns
<b>WdfObjectAllocateContext</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>The <b>ContextTypeInfo</b> member of the WDF_OBJECT_ATTRIBUTES structure that the <i>ContextAttributes</i> parameter specified was invalid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Context space could not be allocated.
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>The driver has already allocated context space that matches the <b>ContextTypeInfo</b> member of the WDF_OBJECT_ATTRIBUTES structure that <i>ContextAttributes</i> specifies. In this situation, the pointer in the <i>Context</i> parameter receives a pointer to the existing context space and does not allocate duplicate context space.
<dl>
<dt><b>STATUS_DELETE_PENDING</b></dt>
</dl>The object that the <i>Handle</i> parameter specifies is being deleted. In this situation, the framework does not allocate context space.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
Typically, drivers create object context space by specifying a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure when they call a framework object's creation method, such as <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. 

If you want your driver to allocate more than one type of context space to some of its objects, the driver can call <b>WdfObjectAllocateContext</b> one or more times after it has called an object's creation method. Each call to <b>WdfObjectAllocateContext</b> must specify a different context type. (The <b>ContextTypeInfo</b> member of the WDF_OBJECT_ATTRIBUTES structure identifies the context type.) 

If your driver calls <b>WdfObjectAllocateContext</b> more than once for a given object, you can provide separate <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for each context.

When calling <b>WdfObjectAllocateContext</b>, do not specify a <b>ParentObject</b> in the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.

When the framework allocates context space for an object, it also zero-initializes the context space.

For more information about object context space, see <a href="https://msdn.microsoft.com/21a46e04-2330-4a3d-ba72-c04295bfbb3c">Framework Object Context Space</a>.

The following code example creates context space for a request object. The context space is based on the example's REQUEST_CONTEXT structure.


## -see-also
<dl>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectAllocateContext method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

