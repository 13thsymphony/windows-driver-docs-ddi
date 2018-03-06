---
UID: NF:wudfddi.IWDFDeviceInitialize.SetLockingConstraint
title: IWDFDeviceInitialize::SetLockingConstraint method
author: windows-driver-content
description: The SetLockingConstraint method sets the synchronization (or locking) model for callback functions into the driver.
old-location: wdf\iwdfdeviceinitialize_setlockingconstraint.htm
old-project: wdf
ms.assetid: c0062ad4-6666-49db-9d53-70f2ed2353d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDeviceInitialize, IWDFDeviceInitialize interface, SetLockingConstraint method, IWDFDeviceInitialize::SetLockingConstraint, SetLockingConstraint method, SetLockingConstraint method, IWDFDeviceInitialize interface, SetLockingConstraint,IWDFDeviceInitialize.SetLockingConstraint, UMDFDeviceObjectRef_ec613925-df47-4231-8f53-3769df71f288.xml, umdf.iwdfdeviceinitialize_setlockingconstraint, wdf.iwdfdeviceinitialize_setlockingconstraint, wudfddi/IWDFDeviceInitialize::SetLockingConstraint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDeviceInitialize.SetLockingConstraint
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# SetLockingConstraint method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetLockingConstraint</b> method sets the synchronization (or locking) model for callback functions into the driver.

## Syntax

````
void SetLockingConstraint(
  [in] WDF_CALLBACK_CONSTRAINT LockType
);
````

## Parameters

`LockType`

A value of type <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_callback_constraint.md">WDF_CALLBACK_CONSTRAINT</a> that identifies the locking model.


## Return Value

This method does not return a value.

## Remarks

The default value of the <i>LockType</i> parameter is <b>WdfDeviceLevel</b>, which is currently the only supported value.


#### Examples

For a code example of how to use the <b>SetLockingConstraint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::SetLockingConstraint method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>