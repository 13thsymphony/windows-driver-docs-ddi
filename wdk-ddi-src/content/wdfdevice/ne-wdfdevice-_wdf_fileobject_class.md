---
UID: NE.wdfdevice._WDF_FILEOBJECT_CLASS
title: _WDF_FILEOBJECT_CLASS
author: windows-driver-content
description: The WDF_FILEOBJECT_CLASS enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open.
old-location: wdf\wdf_fileobject_class.htm
old-project: wdf
ms.assetid: e0887061-eafe-4dba-bb7a-58bf949e2d08
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_FILEOBJECT_CLASS, WDF_FILEOBJECT_CLASS, *PWDF_FILEOBJECT_CLASS
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
req.alt-api: WDF_FILEOBJECT_CLASS
req.alt-loc: wdfdevice.h
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

# _WDF_FILEOBJECT_CLASS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_FILEOBJECT_CLASS</b> enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open. These values also specify where the framework can store the object's handle.



## -syntax

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


## -enum-fields

### -field WdfFileObjectInvalid

Reserved for internal use.


### -field WdfFileObjectNotRequired

The driver does not require a framework file object.


### -field WdfFileObjectWdfCanUseFsContext

The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext</b> member of the file's Windows Driver Model (WDM) <a href="kernel.file_object">FILE_OBJECT</a> structure.


### -field WdfFileObjectWdfCanUseFsContext2

The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure.


### -field WdfFileObjectWdfCannotUseFsContexts

The driver requires a framework file object. The framework cannot store the object's handle in the <b>FsContext</b> or <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure, because one or more drivers are using these members. Therefore, the framework must store the handle internally.


### -field WdfFileObjectCanBeOptional

The driver typically requires a framework file object, but the driver can also handle special situations in which a framework file object is missing or different. For more information about these situations, see the following Remarks section. 

<b>WdfFileObjectCanBeOptional</b> is a bit flag that your driver can OR with the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> enumerator value. 

Most framework-based drivers do not use this bit flag.

The <b>WdfFileObjectCanBeOptional</b> value is available in version 1.9 and later versions of KMDF.


## -remarks
The <b>WDF_FILEOBJECT_CLASS</b> enumeration is used in the <a href="wdf.wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a> structure.

If your driver calls <a href="wdf.wdfrequestgetfileobject">WdfRequestGetFileObject</a> to obtain framework file objects for I/O requests, and if you know that some of the WDM I/O request packets (IRPs) that your driver receives do not include WDM file objects, the driver can set the <b>WdfFileObjectCanBeOptional</b> bit flag. 

If your driver sets the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> value and does <i>not</i> set the <b>WdfFileObjectCanBeOptional</b> bit flag, <a href="wdf.using_kmdf_verifier">the framework's verifier</a> reports an error for the following cases when the driver calls the <a href="wdf.wdfrequestgetfileobject">WdfRequestGetFileObject</a> method: 

An IRP does not include a WDM file object.

An IRP includes a WDM file object, but the file object is different from the one that the file creation IRP included.

If the <b>WdfFileObjectCanBeOptional</b> bit flag is set, the framework's verifier ignores such cases.


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
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.file_object">FILE_OBJECT</a>
</dt>
<dt>
<a href="wdf.wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_FILEOBJECT_CLASS enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

