---
UID: NF:wdfchildlist.WdfChildListUpdateAllChildDescriptionsAsPresent
title: WdfChildListUpdateAllChildDescriptionsAsPresent function
author: windows-driver-content
description: The WdfChildListUpdateAllChildDescriptionsAsPresent method informs the framework that all of the child devices in a specified child list are plugged in and available.
old-location: wdf\wdfchildlistupdateallchilddescriptionsaspresent.htm
old-project: wdf
ms.assetid: 598d2b4f-9b49-480a-9cf8-25661c24483f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfChildListUpdateAllChildDescriptionsAsPresent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfChildListUpdateAllChildDescriptionsAsPresent
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
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListUpdateAllChildDescriptionsAsPresent function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method informs the framework that all of the child devices in a specified child list are plugged in and available.



## -syntax

````
VOID WdfChildListUpdateAllChildDescriptionsAsPresent(
  _In_ WDFCHILDLIST ChildList
);
````


## -parameters

### -param ChildList [in]

A handle to a child list object.


## -returns
None.

A system bug check occurs if the driver supplies an invalid object handle.



## -remarks
The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method is available in version 1.0 and later versions of KMDF.

For more information about child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

The following code example informs the framework that all of the devices that a device list represents are plugged in and available.</p>