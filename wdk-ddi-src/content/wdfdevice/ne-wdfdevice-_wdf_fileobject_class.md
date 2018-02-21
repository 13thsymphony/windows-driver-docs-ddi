---
UID: NE:wdfdevice._WDF_FILEOBJECT_CLASS
title: "_WDF_FILEOBJECT_CLASS"
author: windows-driver-content
description: The WDF_FILEOBJECT_CLASS enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open.
old-location: wdf\wdf_fileobject_class.htm
old-project: wdf
ms.assetid: e0887061-eafe-4dba-bb7a-58bf949e2d08
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFFileObjectRef_001acbc3-7e2c-4b8b-ab14-024653cefe19.xml, PWDF_FILEOBJECT_CLASS, WdfFileObjectInvalid, wdfdevice/WdfFileObjectWdfCannotUseFsContexts, PWDF_FILEOBJECT_CLASS enumeration pointer, WdfFileObjectWdfCanUseFsContext2, wdfdevice/WDF_FILEOBJECT_CLASS, wdfdevice/WdfFileObjectWdfCanUseFsContext2, _WDF_FILEOBJECT_CLASS, wdf.wdf_fileobject_class, WdfFileObjectWdfCannotUseFsContexts, wdfdevice/WdfFileObjectWdfCanUseFsContext, WDF_FILEOBJECT_CLASS enumeration, kmdf.wdf_fileobject_class, wdfdevice/WdfFileObjectCanBeOptional, wdfdevice/WdfFileObjectNotRequired, WdfFileObjectNotRequired, *PWDF_FILEOBJECT_CLASS, wdfdevice/PWDF_FILEOBJECT_CLASS, WdfFileObjectWdfCanUseFsContext, wdfdevice/WdfFileObjectInvalid, WDF_FILEOBJECT_CLASS, WdfFileObjectCanBeOptional
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_FILEOBJECT_CLASS
product: Windows
targetos: Windows
req.typenames: "*PWDF_FILEOBJECT_CLASS, WDF_FILEOBJECT_CLASS"
req.product: Windows 10 or later.
---

# _WDF_FILEOBJECT_CLASS Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_FILEOBJECT_CLASS</b> enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open. These values also specify where the framework can store the object's handle.

## Syntax
````
typedef enum _WDF_FILEOBJECT_CLASS { 
  WdfFileObjectInvalid                 = 0,
  WdfFileObjectNotRequired             = 1,
  WdfFileObjectWdfCanUseFsContext      = 2,
  WdfFileObjectWdfCanUseFsContext2     = 3,
  WdfFileObjectWdfCannotUseFsContexts  = 4,
  WdfFileObjectCanBeOptional           = 0x80000000
} WDF_FILEOBJECT_CLASS, *PWDF_FILEOBJECT_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>WdfFileObjectCanBeOptional</td>
                    <td>The driver typically requires a framework file object, but the driver can also handle special situations in which a framework file object is missing or different. For more information about these situations, see the following Remarks section. 

<b>WdfFileObjectCanBeOptional</b> is a bit flag that your driver can OR with the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> enumerator value. 

Most framework-based drivers do not use this bit flag.

The <b>WdfFileObjectCanBeOptional</b> value is available in version 1.9 and later versions of KMDF.</td>
                </tr>
            
                <tr>
                    <td>WdfFileObjectInvalid</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>WdfFileObjectNotRequired</td>
                    <td>The driver does not require a framework file object.</td>
                </tr>
            
                <tr>
                    <td>WdfFileObjectWdfCannotUseFsContexts</td>
                    <td>The driver requires a framework file object. The framework cannot store the object's handle in the <b>FsContext</b> or <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure, because one or more drivers are using these members. Therefore, the framework must store the handle internally.</td>
                </tr>
            
                <tr>
                    <td>WdfFileObjectWdfCanUseFsContext</td>
                    <td>The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext</b> member of the file's Windows Driver Model (WDM) <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure.</td>
                </tr>
            
                <tr>
                    <td>WdfFileObjectWdfCanUseFsContext2</td>
                    <td>The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure.</td>
                </tr>
</table>

## Remarks

The <b>WDF_FILEOBJECT_CLASS</b> enumeration is used in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_fileobject_config.md">WDF_FILEOBJECT_CONFIG</a> structure.

If your driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a> to obtain framework file objects for I/O requests, and if you know that some of the WDM I/O request packets (IRPs) that your driver receives do not include WDM file objects, the driver can set the <b>WdfFileObjectCanBeOptional</b> bit flag. 

If your driver sets the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> value and does <i>not</i> set the <b>WdfFileObjectCanBeOptional</b> bit flag, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error for the following cases when the driver calls the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a> method: 

<ul>
<li>
An IRP does not include a WDM file object.

</li>
<li>
An IRP includes a WDM file object, but the file object is different from the one that the file creation IRP included.

</li>
</ul>
If the <b>WdfFileObjectCanBeOptional</b> bit flag is set, the framework's verifier ignores such cases.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_fileobject_config.md">WDF_FILEOBJECT_CONFIG</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_FILEOBJECT_CLASS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>