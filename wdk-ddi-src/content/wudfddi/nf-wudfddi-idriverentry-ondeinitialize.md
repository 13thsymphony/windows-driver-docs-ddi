---
UID: NF:wudfddi.IDriverEntry.OnDeinitialize
title: IDriverEntry::OnDeinitialize method
author: windows-driver-content
description: The OnDeinitialize method performs any operations that are necessary before a system unloads a driver.
old-location: wdf\idriverentry_ondeinitialize.htm
old-project: wdf
ms.assetid: 9366029e-4f8b-4121-ad99-01a5116a7f46
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IDriverEntry, IDriverEntry::OnDeinitialize, OnDeinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDriverEntry.OnDeinitialize
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IDriverEntry::OnDeinitialize method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDeinitialize</b> method performs any operations that are necessary before a system unloads a driver.



## -syntax

````
void OnDeinitialize(
  [in] IWDFDriver *pWdfDriver
);
````


## -parameters

### -param pWdfDriver [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface for the driver object that represents the driver that the system unloads.


## -returns
None


## -remarks
The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver is about to be unloaded from the host process, the framework calls <b>OnDeinitialize</b> to notify the driver of the departure and passes the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface in the call. The system unloads the driver after <b>OnDeinitialize</b> returns. 


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-idriverentry.md">IDriverEntry</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IDriverEntry::OnDeinitialize method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

