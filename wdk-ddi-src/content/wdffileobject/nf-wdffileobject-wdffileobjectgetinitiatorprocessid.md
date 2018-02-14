---
UID: NF:wdffileobject.WdfFileObjectGetInitiatorProcessId
title: WdfFileObjectGetInitiatorProcessId function
author: windows-driver-content
description: The WdfFileObjectGetInitiatorProcessId function retrieves the initiator process ID that is associated with a specified framework file object.
old-location: wdf\wdffileobjectgetinitiatorprocessid.htm
old-project: wdf
ms.assetid: 59E15EAA-4934-48D9-A9E3-7CDEEAE01985
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfFileObjectGetInitiatorProcessId function, WdfFileObjectGetInitiatorProcessId, wdf.wdffileobjectgetinitiatorprocessid, wdffileobject/WdfFileObjectGetInitiatorProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WUDFx02000.dll
apiname:
-	WdfFileObjectGetInitiatorProcessId
product: Windows
targetos: Windows
req.typenames: "*PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS"
req.product: Windows 10 or later.
---


# WdfFileObjectGetInitiatorProcessId function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFileObjectGetInitiatorProcessId</b> function retrieves the initiator process ID that is associated with a specified framework file object.

## Syntax

````
ULONG WdfFileObjectGetInitiatorProcessId(
  _In_ WDFFILEOBJECT FileObject
);
````

## Parameters

`FileObject`

A handle to a framework file object.


## Return Value

Returns the initiator process identifier associated with the file, if any exists. Otherwise, the function returns zero.

## Remarks

Starting in Windows 8, a system component may issue a create on behalf of an application. The driver can call <b>WdfFileObjectGetInitiatorProcessId</b> to determine which process the create operation is ultimately intended for.

<b>WdfFileObjectGetInitiatorProcessId</b> returns zero if no initiator process is associated with the create operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.21 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdffileobject.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.lib |
| **DLL** | WUDFx02000.dll |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetrequestorprocessid.md">WdfRequestGetRequestorProcessId</a>



<a href="https://msdn.microsoft.com/4D23A651-7231-40CE-B9C2-4382D4E7F683">IWDFDevice3::GetInitiatorProcessId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFileObjectGetInitiatorProcessId function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>