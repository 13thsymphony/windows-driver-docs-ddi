---
UID: NF:wudfddi.IWDFDeviceInitialize.AutoForwardCreateCleanupClose
title: IWDFDeviceInitialize::AutoForwardCreateCleanupClose method
author: windows-driver-content
description: The AutoForwardCreateCleanupClose method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.
old-location: wdf\iwdfdeviceinitialize_autoforwardcreatecleanupclose.htm
old-project: wdf
ms.assetid: b9c8e54e-7cd5-48a9-b948-5327900c8a99
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDeviceInitialize::AutoForwardCreateCleanupClose, AutoForwardCreateCleanupClose method, IWDFDeviceInitialize interface, wudfddi/IWDFDeviceInitialize::AutoForwardCreateCleanupClose, AutoForwardCreateCleanupClose method, AutoForwardCreateCleanupClose, wdf.iwdfdeviceinitialize_autoforwardcreatecleanupclose, IWDFDeviceInitialize, umdf.iwdfdeviceinitialize_autoforwardcreatecleanupclose, UMDFDeviceObjectRef_6f68d9cd-cfb9-49ae-94b8-a230e4dc0762.xml, IWDFDeviceInitialize interface, AutoForwardCreateCleanupClose method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDeviceInitialize.AutoForwardCreateCleanupClose
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# AutoForwardCreateCleanupClose method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AutoForwardCreateCleanupClose</b> method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.

## Syntax

````
void AutoForwardCreateCleanupClose(
  [in] WDF_TRI_STATE State
);
````

## Parameters

`State`

A WDF_TRI_STATE-typed value that identifies the state of automatic forwarding. The following table shows the possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>WdfUseDefault</b> (0)

</td>
<td>
The framework uses the default forwarding scheme. For more information, see the following Remarks section.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
The framework does not forward create, cleanup, and close notifications to the next lower driver.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
The framework synchronously forwards create, cleanup, and close notifications to the next lower driver.

</td>
</tr>
</table>


## Return Value

None

## Remarks

If the UMDF driver passes <b>WdfUseDefault</b> for the <i>State</i> parameter in a call to <b>AutoForwardCreateCleanupClose</b>, the framework uses a default forwarding scheme for create, cleanup, and close notifications that depends on whether the driver is a filter or function driver:

<ul>
<li>
If the driver is a filter driver, the default forwarding scheme is to synchronously forward notifications to the next lower driver.

</li>
<li>
If the driver is a function driver, the default forwarding scheme is not to forward notifications to the next lower driver.

</li>
</ul>
If the framework is set up for forwarding, it forwards cleanup and close notifications regardless of whether the driver supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554910">IFileCallbackClose::OnCloseFile</a> interface methods. However, the framework automatically forwards create requests only if the driver does not support the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> method. If the driver supports <b>IQueueCallbackCreate::OnCreateFile</b>, the framework forwards create requests only if the driver explicitly set up forwarding (<b>WdfTrue</b>) to the next lower driver. 

For more information about how a UMDF driver uses <b>AutoForwardCreateCleanupClose</b>, see <a href="https://msdn.microsoft.com/e6678226-44d3-4b1d-a296-2017bc9c7c37">Preventing an Imbalance of Create and Close Notifications to a Driver</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554910">IFileCallbackClose::OnCloseFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::AutoForwardCreateCleanupClose method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>