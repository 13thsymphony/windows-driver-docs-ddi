---
UID: NF:wdfobject.WdfObjectReferenceActual
title: WdfObjectReferenceActual function
author: windows-driver-content
description: The WdfObjectReferenceActual method increments the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.
old-location: wdf\wdfobjectreferenceactual.htm
old-project: wdf
ms.assetid: d0bb58c1-1036-496a-b108-c0d5e5de3bc2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfObjectReferenceActual
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
req.alt-api: WdfObjectReferenceActual
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

# WdfObjectReferenceActual function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectReferenceActual</b> method increments the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.



## -syntax

````
VOID WdfObjectReferenceActual(
  _In_     WDFOBJECT Handle,
  _In_opt_ PVOID     Tag,
  _In_     LONG      Line,
  _In_     PCCH      File
);
````


## -parameters

### -param Handle [in]

A handle to a framework object.


### -param Tag [in, optional]

A driver-defined value that the framework stores as an identification tag for the object reference.


### -param Line [in]

A numeric value that represents a line number in a driver source file.


### -param File [in]

A pointer to a null-terminated constant character string that represents the name of a driver source file. This parameter is optional and can be <b>NULL</b>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If your driver calls <b>WdfObjectReferenceActual</b> to increment a reference count, the driver must call <a href="..\wdfobject\nf-wdfobject-wdfobjectdereferenceactual.md">WdfObjectDereferenceActual</a> to decrement the count.

Calling <b>WdfObjectReferenceActual</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548763">WdfObjectReferenceWithTag</a> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> provides additional information (tag value, line number, and file name) to Microsoft debuggers. <b>WdfObjectReferenceActual</b> allows your driver to specify the line number and file name, while <b>WdfObjectReferenceWithTag</b> uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the <b>!wdftagtracker</b> debugger extension. The debugger extension displays the tag value as both a pointer and a series of characters. For more about debugger extensions, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.

For more information about object reference counts, see <a href="https://msdn.microsoft.com/33efc3a8-ac46-4626-ba0f-beb1eaa9ee47">Framework Object Life Cycle</a>.

The following code example increments an object's reference count and assigns a tag value, line number, and file name to the reference.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectReferenceActual method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

