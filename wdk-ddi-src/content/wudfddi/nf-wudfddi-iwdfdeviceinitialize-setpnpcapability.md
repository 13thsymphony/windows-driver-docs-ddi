---
UID: NF:wudfddi.IWDFDeviceInitialize.SetPnpCapability
title: IWDFDeviceInitialize::SetPnpCapability method
author: windows-driver-content
description: The SetPnpCapability method sets the specified Plug and Play (PnP) capability of a device to the specified state.
old-location: wdf\iwdfdeviceinitialize_setpnpcapability.htm
old-project: wdf
ms.assetid: 82892740-12f6-469b-a65c-6905d32c0b0d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDeviceInitialize, IWDFDeviceInitialize interface, SetPnpCapability method, IWDFDeviceInitialize::SetPnpCapability, SetPnpCapability method, SetPnpCapability method, IWDFDeviceInitialize interface, SetPnpCapability,IWDFDeviceInitialize.SetPnpCapability, UMDFDeviceObjectRef_516aeba5-c0c2-40a0-a9e6-d1a983835a94.xml, umdf.iwdfdeviceinitialize_setpnpcapability, wdf.iwdfdeviceinitialize_setpnpcapability, wudfddi/IWDFDeviceInitialize::SetPnpCapability
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
-	IWDFDeviceInitialize.SetPnpCapability
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFDeviceInitialize::SetPnpCapability method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPnpCapability</b> method sets the specified Plug and Play (PnP) capability of a device to the specified state.

## Syntax

```
void SetPnpCapability(
  WDF_PNP_CAPABILITY Capability,
  WDF_TRI_STATE      Value
);
```

## Parameters

`Capability`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561428">WDF_PNP_CAPABILITY</a>-typed value that identifies the PnP capability to set.

`Value`

A WDF_TRI_STATE-typed value that identifies how to set the PnP capability that is specified by <i>Capability</i>. The following table shows the possible values.

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
Set the capability to the default state.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
Do not set the capability.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
Set the capability.

</td>
</tr>
</table>


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561428">WDF_PNP_CAPABILITY</a>