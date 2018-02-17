---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrievePowerPolicy
title: IWDFUsbTargetDevice::RetrievePowerPolicy method
author: windows-driver-content
description: The RetrievePowerPolicy method retrieves a WinUsb power policy.
old-location: wdf\iwdfusbtargetdevice_retrievepowerpolicy.htm
old-project: wdf
ms.assetid: e15561e3-ba3d-4c65-bb6e-d90f3fab22af
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RetrievePowerPolicy, RetrievePowerPolicy method, IWDFUsbTargetDevice interface, UMDFUSBref_50da7595-0735-475b-863e-33a689f4fc2b.xml, RetrievePowerPolicy method, wudfusb/IWDFUsbTargetDevice::RetrievePowerPolicy, IWDFUsbTargetDevice::RetrievePowerPolicy, umdf.iwdfusbtargetdevice_retrievepowerpolicy, IWDFUsbTargetDevice, wdf.iwdfusbtargetdevice_retrievepowerpolicy, IWDFUsbTargetDevice interface, RetrievePowerPolicy method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
req.lib: wudfusb.h
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
-	IWDFUsbTargetDevice.RetrievePowerPolicy
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# RetrievePowerPolicy method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrievePowerPolicy</b> method retrieves a WinUsb power policy.

## Syntax

````
HRESULT RetrievePowerPolicy(
  [in]      ULONG PolicyType,
  [in, out] ULONG *ValueLength,
  [out]     PVOID Value
);
````

## Parameters

`PolicyType`

The type of WinUsb power policy that the UMDF driver requests.

`ValueLength`

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that <b>RetrievePowerPolicy</b> supplies in <i>Value</i>. On output, this parameter contains the size that <b>RetrievePowerPolicy</b> requires for <i>Value</i>.

`Value`

A pointer that receives the buffer that contains the WinUsb power policy.


## Return Value

<b>RetrievePowerPolicy</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/e15561e3-ba3d-4c65-bb6e-d90f3fab22af">RetrievePowerPolicy</a> successfully retrieved the WinUsb power policy. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/e15561e3-ba3d-4c65-bb6e-d90f3fab22af">RetrievePowerPolicy</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>

## Remarks

Power policy controls the power management that WinUsb for the device performs.

For information about valid policy types that a UMDF driver can pass for the <i>PolicyType</i> parameter and values that the framework returns, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540275">WinUsb_GetPowerPolicy</a> function.

For more information about the power behavior of WinUSB, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff728834">WinUSB Power Management</a>.

The <b>RetrievePowerPolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **Library** | wudfusb.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560385">IWDFUsbTargetDevice::SetPowerPolicy</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540275">WinUsb_GetPowerPolicy</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::RetrievePowerPolicy method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>