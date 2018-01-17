---
UID: NC:wdfpdo.PFN_WDFPDOMARKMISSING
title: PFN_WDFPDOMARKMISSING function
author: windows-driver-content
description: The WdfPdoMarkMissing method informs the framework that a device is no longer accessible.
old-location: wdf\wdfpdomarkmissing.htm
old-project: wdf
ms.assetid: f35e1ed4-eaa9-423c-95cb-5eb96231d592
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFPDOMARKMISSING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfPdoMarkMissing
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# PFN_WDFPDOMARKMISSING function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoMarkMissing</b> method informs the framework that a device is no longer accessible.



## -syntax

````
NTSTATUS WdfPdoMarkMissing(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


## -returns
If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Device</i> handle does not represent a PDO.
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>The device object could not be found.

 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.


## -remarks
For more information about <b>WdfPdoMarkMissing</b>, see <a href="https://msdn.microsoft.com/58377f17-a9dc-4096-af23-36f8d8dbb87e">Static Enumeration</a>.

The following code example searches a list of child devices to find one that matches a specified serial number. When the example finds the correct child, it calls <b>WdfPdoMarkMissing</b> to indicate that the child is not accessible. This example was taken from the <a href="wdf.sample_kmdf_drivers">Toaster</a> sample bus driver and simplified.


## -see-also
<dl>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdoretrievenextstaticchild.md">WdfFdoRetrieveNextStaticChild</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md">WdfFdoUnlockStaticChildListFromIteration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoMarkMissing method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

