---
UID: NF:wdfdevice.WdfDeviceGetFileObject
title: WdfDeviceGetFileObject function
author: windows-driver-content
description: The WdfDeviceGetFileObject method returns a handle to the framework file object that is associated with a specified WDM file object.
old-location: wdf\wdfdevicegetfileobject.htm
old-project: wdf
ms.assetid: 2e56d444-4248-4f00-b712-cbb3a4869302
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_5aa48187-4a28-424c-9cd1-76cb5a33dc75.xml, WdfDeviceGetFileObject, WdfDeviceGetFileObject method, kmdf.wdfdevicegetfileobject, wdf.wdfdevicegetfileobject, wdfdevice/WdfDeviceGetFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceGetFileObject
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetFileObject function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetFileObject</b> method returns a handle to the framework file object that is associated with a specified WDM file object.

## Syntax

````
WDFFILEOBJECT WdfDeviceGetFileObject(
  _In_ WDFDEVICE    Device,
  _In_ PFILE_OBJECT FileObject
);
````

## Parameters

`Device`

A handle to a framework device object.

`FileObject`

A pointer to a WDM <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure.


## Return Value

<b>WdfDeviceGetFileObject</b> returns a handle to the framework file object that is associated with the specified WDM file object. If a framework file object was not created for the file, or if the <i>FileObject</i> pointer is invalid, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

The following code example obtains a pointer to a named WDM device object and its corresponding WDM file object, if the requested access to the objects can be granted. Then, the example obtains a handle to the framework file object that is associated with the WDM file object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PFILE_OBJECT  pWdmFileObject = NULL;
PDEVICE_OBJECT  pWdmDeviceObject = NULL;
WDFFILEOBJECT  fileObject = NULL;
NTSTATUS  status = STATUS_SUCCESS;
BOOLEAN  success = TRUE;

status = IoGetDeviceObjectPointer(
                                  &amp;inputFileName,    // File name 
                                  FILE_ALL_ACCESS,   // Access mask
                                  &amp;pWdmFileObject,   // Output pointer of WDM file object
                                  &amp;pWdmDeviceObject  // Output pointer of WDM device object
                                  );

if(!NT_SUCCESS(status)){
    success = FALSE;
    break;
}

fileObject = WdfDeviceGetFileObject(
                                    gDeviceObject,  // Handle to device object
                                    pWdmFileObject  // Handle to WDM file object
                                    );
if(fileObject == NULL){
    success = FALSE;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>