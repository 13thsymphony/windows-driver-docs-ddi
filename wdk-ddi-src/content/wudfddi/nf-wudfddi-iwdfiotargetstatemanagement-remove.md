---
UID: NF:wudfddi.IWDFIoTargetStateManagement.Remove
title: IWDFIoTargetStateManagement::Remove method
author: windows-driver-content
description: The Remove method removes a local I/O target.
old-location: wdf\iwdfiotargetstatemanagement_remove.htm
old-project: wdf
ms.assetid: 28a802b3-f916-4455-a93a-868393a570cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoTargetStateManagement, IWDFIoTargetStateManagement interface, Remove method, IWDFIoTargetStateManagement::Remove, Remove method, Remove method, IWDFIoTargetStateManagement interface, Remove,IWDFIoTargetStateManagement.Remove, UMDFIoTargetObjectRef_aad5b1f1-14c0-442f-a289-be006b20816e.xml, umdf.iwdfiotargetstatemanagement_remove, wdf.iwdfiotargetstatemanagement_remove, wudfddi/IWDFIoTargetStateManagement::Remove
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
req.lib: 
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
-	IWDFIoTargetStateManagement.Remove
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoTargetStateManagement::Remove method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Remove</b> method removes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

## Syntax

```
HRESULT Remove(
  BOOL bIsSurpriseRemove
);
```

## Parameters

`bIsSurpriseRemove`

A BOOL value which, if <b>TRUE</b>, specifies that the device was unexpectly removed ("surprise removal").   However, the framework ignores this parameter.


## Return Value

<b>Remove</b> always returns S_OK.

## Remarks

Although the <b>Remove</b> method is available, drivers do not need to call it.  If a driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff558930">IWDFFileHandleTargetFactory::CreateFileHandleTarget</a> to create a file-handle-based I/O target,  the driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> to delete the I/O target object after the driver has finished using the file-handle-based target. The <b>DeleteWdfObject</b> method performs the operations that <b>Remove</b> performs, along with additional operations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559198">IWDFIoTargetStateManagement</a>