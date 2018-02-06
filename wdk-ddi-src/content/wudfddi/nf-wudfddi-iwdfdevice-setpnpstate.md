---
UID: NF:wudfddi.IWDFDevice.SetPnpState
title: IWDFDevice::SetPnpState method
author: windows-driver-content
description: The SetPnpState method turns on or off (or sets to the default state) the specified Plug and Play (PnP) property of a device.
old-location: wdf\iwdfdevice_setpnpstate.htm
old-project: wdf
ms.assetid: 3bd88ecd-7c7c-4ee9-8eb8-bc5653bd4ed0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/IWDFDevice::SetPnpState, wdf.iwdfdevice_setpnpstate, SetPnpState method, IWDFDevice interface, SetPnpState method, UMDFDeviceObjectRef_1efea639-31d7-4420-8b8a-c528597ceffb.xml, SetPnpState method, IWDFDevice interface, IWDFDevice::SetPnpState, SetPnpState, IWDFDevice, umdf.iwdfdevice_setpnpstate
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
-	IWDFDevice.SetPnpState
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# SetPnpState method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPnpState</b> method turns on or off (or sets to the default state) the specified Plug and Play (PnP) property of a device.

## Syntax

````
void SetPnpState(
  [in] WDF_PNP_STATE State,
  [in] WDF_TRI_STATE Value
);
````

## Parameters

`State`

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a>-typed value that identifies the PnP property to set.

`Value`

A WDF_TRI_STATE-typed value that identifies how to set the PnP property that <i>State</i> specifies. The following table shows the possible values for <i>Value</i>.
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
Set the PnP property to the default state.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
Turn off the PnP property.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
Turn on the PnP property.

</td>
</tr>
</table>


## Return Value

None

## Remarks

Before the state of the PnP property that <b>SetPnpState</b> set can take effect, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557010">IWDFDevice::CommitPnpState</a> method.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557010">IWDFDevice::CommitPnpState</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558834">IWDFDevice::GetPnpState</a>

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::SetPnpState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>