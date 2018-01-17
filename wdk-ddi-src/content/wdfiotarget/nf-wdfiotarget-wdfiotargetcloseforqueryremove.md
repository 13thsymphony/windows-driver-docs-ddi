---
UID: NF:wdfiotarget.WdfIoTargetCloseForQueryRemove
title: WdfIoTargetCloseForQueryRemove function
author: windows-driver-content
description: The WdfIoTargetCloseForQueryRemove method temporarily closes a specified remote I/O target because the target device might soon be removed.
old-location: wdf\wdfiotargetcloseforqueryremove.htm
old-project: wdf
ms.assetid: 5fa93ac6-8aee-4248-b0a6-ab82bc5486bf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoTargetCloseForQueryRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfIoTargetCloseForQueryRemove
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetCloseForQueryRemove function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetCloseForQueryRemove</b> method temporarily closes a specified <a href="wdf.general_i_o_targets">remote I/O target</a> because the target device might soon be removed.



## -syntax

````
VOID WdfIoTargetCloseForQueryRemove(
  _In_ WDFIOTARGET IoTarget
);
````


## -parameters

### -param IoTarget [in]

A handle to a remote I/O target object that was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Drivers that supply an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function must call <b>WdfIoTargetCloseForQueryRemove</b> from within that callback function, if the driver determines that the target device can be safely removed. 

For more information about <b>WdfIoTargetCloseForQueryRemove</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

The following code example is the <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function from the <a href="wdf.sample_kmdf_drivers">Toaster</a> sample driver. The function stops a timer, ensures that a previously submitted work item has been serviced, and then calls <b>WdfIoTargetCloseForQueryRemove</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetCloseForQueryRemove method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

