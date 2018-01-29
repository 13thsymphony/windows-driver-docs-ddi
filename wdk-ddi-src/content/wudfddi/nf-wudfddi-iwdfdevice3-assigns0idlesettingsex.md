---
UID : NF:wudfddi.IWDFDevice3.AssignS0IdleSettingsEx
title : IWDFDevice3::AssignS0IdleSettingsEx method
author : windows-driver-content
description : The AssignS0IdleSettingsEx method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location : wdf\iwdfdevice3_assigns0idlesettingsex.htm
old-project : wdf
ms.assetid : D020B8AA-7353-47E1-A111-82BFE6F5F03D
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : umdf.iwdfdevice3_assigns0idlesettingsex, IWDFDevice3, IWDFDevice3::AssignS0IdleSettingsEx, AssignS0IdleSettingsEx method, IWDFDevice3 interface, AssignS0IdleSettingsEx, wdf.iwdfdevice3_assigns0idlesettingsex, wudfddi/IWDFDevice3::AssignS0IdleSettingsEx, AssignS0IdleSettingsEx method, IWDFDevice3 interface, AssignS0IdleSettingsEx method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
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
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# AssignS0IdleSettingsEx method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
  <b>AssignS0IdleSettingsEx</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.

## Syntax

````
HRESULT AssignS0IdleSettingsEx(
  [in] PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS IdleSettings
);
````

## Parameters

`IdleSettings`

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure that was initialized by a call to the <a href="..\wudfdevice\nf-wudfdevice-wudf_device_power_policy_idle_settings_init.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a> macro.


## Return Value

The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

A driver can call <b>AssignS0IdleSettingsEx</b> at any point after the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>. Before calling  <b>IWDFDriver::CreateDevice</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557001">IWDFDeviceInitialize::SetPowerPolicyOwnership</a> with  the <i>fTrue</i> parameter set to <b>TRUE</b>. For an example of this call sequence, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

If your driver calls <b>AssignS0IdleSettingsEx</b> more than once, follow the rules described in the Remarks section of <a href="https://msdn.microsoft.com/ffe91b9a-3b74-4dd9-b23d-096f1992485e">AssignS0IdleSettings</a>.

For more information about idle power-down, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556920">IWDFDevice2::AssignS0IdleSettings</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigns0idlesettings.md">WdfDeviceAssignS0IdleSettings</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::AssignS0IdleSettingsEx method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>