---
UID : NF:wudfddi.IWDFIoTargetStateManagement.Remove
title : IWDFIoTargetStateManagement::Remove method
author : windows-driver-content
description : The Remove method removes a local I/O target.
old-location : wdf\iwdfiotargetstatemanagement_remove.htm
old-project : wdf
ms.assetid : 28a802b3-f916-4455-a93a-868393a570cf
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : umdf.iwdfiotargetstatemanagement_remove, Remove method, IWDFIoTargetStateManagement interface, wdf.iwdfiotargetstatemanagement_remove, UMDFIoTargetObjectRef_aad5b1f1-14c0-442f-a289-be006b20816e.xml, IWDFIoTargetStateManagement::Remove, IWDFIoTargetStateManagement, Remove, wudfddi/IWDFIoTargetStateManagement::Remove, IWDFIoTargetStateManagement interface, Remove method, Remove method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : POWER_ACTION, *PPOWER_ACTION
req.product : Windows 10 or later.
---


# Remove method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Remove</b> method removes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.

## Syntax

````
HRESULT Remove(
  [in] BOOL bIsSurpriseRemove
);
````

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
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfiotargetstatemanagement.md">IWDFIoTargetStateManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTargetStateManagement::Remove method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>