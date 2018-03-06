---
UID: NF:wudfwdm.InitializeObjectAttributes
title: InitializeObjectAttributes macro
author: windows-driver-content
description: The InitializeObjectAttributes macro initializes the opaque OBJECT_ATTRIBUTES structure, which specifies the properties of an object handle to routines that open handles.
old-location: kernel\initializeobjectattributes.htm
old-project: kernel
ms.assetid: ee89a9af-0bdf-476e-b4e3-eb60662e160d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: InitializeObjectAttributes, InitializeObjectAttributes macro [Kernel-Mode Driver Architecture], k107_f7e00cf9-9598-4835-b51a-3df9e003587e.xml, kernel.initializeobjectattributes, wudfwdm/InitializeObjectAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntdef.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfwdm.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfwdm.h
api_name:
-	InitializeObjectAttributes
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---


# InitializeObjectAttributes function
The <b>InitializeObjectAttributes</b> macro initializes the opaque <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure, which specifies the properties of an object handle to routines that open handles.

## Syntax

````
VOID InitializeObjectAttributes(
  [out]          POBJECT_ATTRIBUTES   InitializedAttributes,
  [in]           PUNICODE_STRING      ObjectName,
  [in]           ULONG                Attributes,
  [in]           HANDLE               RootDirectory,
  [in, optional] PSECURITY_DESCRIPTOR SecurityDescriptor
);
````

## Parameters

`p`

TBD

`n`

TBD

`a`

TBD

`r`

TBD

`s`

TBD


## Return Value

None

## Remarks

<b>InitializeObjectAttributes</b> initializes an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the properties of an object handle to be opened. The caller can then pass a pointer to this structure to a routine that actually opens the handle. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE flag for the <i>Attributes</i> parameter. This flag restricts the use of a handle opened for that object to processes running only in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

Note that <b>InitializeObjectAttributes</b> always sets the <b>SecurityQualityOfService</b> member of <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> to <b>NULL</b>. Drivers that require a non-<b>NULL</b> value can set <b>SecurityQualityOfService</b> directly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntdef.h) |
| **Library** | wudfwdm.h |

## See Also

<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>



<a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>



<a href="..\wdm\nf-wdm-zwopensymboliclinkobject.md">ZwOpenSymbolicLinkObject</a>



<a href="..\wdm\nf-wdm-zwmaketemporaryobject.md">ZwMakeTemporaryObject</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-zwopensection.md">ZwOpenSection</a>



<a href="..\wdm\nf-wdm-zwcreatedirectoryobject.md">ZwCreateDirectoryObject</a>



<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>



<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InitializeObjectAttributes macro%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>