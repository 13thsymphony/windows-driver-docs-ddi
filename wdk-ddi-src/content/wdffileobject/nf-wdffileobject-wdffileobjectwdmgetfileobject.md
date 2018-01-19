---
UID : NF:wdffileobject.WdfFileObjectWdmGetFileObject
title : WdfFileObjectWdmGetFileObject function
author : windows-driver-content
description : The WdfFileObjectWdmGetFileObject method returns the Windows Driver Model (WDM) file object that is associated with a specified framework file object.
old-location : wdf\wdffileobjectwdmgetfileobject.htm
old-project : wdf
ms.assetid : f3cc9b23-6140-4cb2-959d-c76f23c697ea
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfFileObjectWdmGetFileObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdffileobject.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfFileObjectWdmGetFileObject
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product : Windows 10 or later.
---


# WdfFileObjectWdmGetFileObject function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFileObjectWdmGetFileObject</b> method returns the Windows Driver Model (WDM) file object that is associated with a specified framework file object.

## Syntax

````
PFILE_OBJECT WdfFileObjectWdmGetFileObject(
  _In_ WDFFILEOBJECT FileObject
);
````

## Parameters

`FileObject`

A handle to a framework file object.


## Return Value

<b>WdfFileObjectWdmGetFileObject</b> returns a pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure that is associated with the specified framework file object, or <b>NULL</b> if there is no WDM file object for the specified framework file object.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The pointer that the <b>WdfFileObjectWdmGetFileObject</b> method returns is valid until the framework file object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the framework file object, the pointer is valid until the callback function returns.

For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

The following code example obtains a handle to the WDM file object that is associated with a specified framework file object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdffileobject.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFileObjectWdmGetFileObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>