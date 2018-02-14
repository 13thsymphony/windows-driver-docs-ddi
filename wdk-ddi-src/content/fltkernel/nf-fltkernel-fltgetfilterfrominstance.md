---
UID: NF:fltkernel.FltGetFilterFromInstance
title: FltGetFilterFromInstance function
author: windows-driver-content
description: The FltGetFilterFromInstance routine returns an opaque filter pointer for the minifilter driver that created the given instance.
old-location: ifsk\fltgetfilterfrominstance.htm
old-project: ifsk
ms.assetid: 2fe73705-4b44-4c75-8677-3325b6be9250
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltGetFilterFromInstance, FltGetFilterFromInstance, FltGetFilterFromInstance routine [Installable File System Drivers], ifsk.fltgetfilterfrominstance, FltApiRef_e_to_o_d03cf921-2e64-49de-9929-39650fd7d03d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetFilterFromInstance
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetFilterFromInstance function
The <b>FltGetFilterFromInstance</b> routine returns an opaque filter pointer for the minifilter driver that created the given instance.

## Syntax

````
NTSTATUS FltGetFilterFromInstance(
  _In_  PFLT_INSTANCE Instance,
  _Out_ PFLT_FILTER   *RetFilter
);
````

## Parameters

`Instance`

Opaque instance pointer for the instance.

`RetFilter`

Pointer to a caller-allocated variable that receives an opaque filter pointer for the minifilter driver. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetFilterFromInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is being torn down. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltGetFilterFromInstance</b> adds a rundown reference to the opaque filter pointer returned in the <i>RetFilter</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetFilterFromInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get an opaque volume pointer for the volume to which a given minifilter driver instance is attached, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumefrominstance.md">FltGetVolumeFromInstance</a>. 

To enumerate all instances of a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetvolumefrominstance.md">FltGetVolumeFromInstance</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetFilterFromInstance routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>