---
UID: NF:wudfddi.IPnpCallbackHardware2.OnPrepareHardware
title: IPnpCallbackHardware2::OnPrepareHardware method
author: windows-driver-content
description: The OnPrepareHardware method performs any operations that are needed to make a device accessible to the driver.
old-location: wdf\ipnpcallbackhardware2_onpreparehardware.htm
old-project: wdf
ms.assetid: 830D706A-016C-4637-829F-2014AD1A1309
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IPnpCallbackHardware2, IPnpCallbackHardware2::OnPrepareHardware, OnPrepareHardware
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IPnpCallbackHardware2.OnPrepareHardware
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackHardware2::OnPrepareHardware method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The <b>OnPrepareHardware</b> method performs any operations that are needed to make a device accessible to the driver.
  



## -syntax

````
HRESULT OnPrepareHardware(
  [in] IWDFDevice3        *pWdfDevice,
  [in] IWDFCmResourceList *pWdfResourcesRaw,
  [in] IWDFCmResourceList *pWdfResourcesTranslated
);
````


## -parameters

### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the framework device object.


### -param pWdfResourcesRaw [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfcmresourcelist.md">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.


### -param pWdfResourcesTranslated [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfcmresourcelist.md">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns
<b>OnPrepareHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

If <b>OnPrepareHardware</b> returns an error code, the framework will still call the <a href="https://msdn.microsoft.com/652B92C2-EF04-482A-BB57-9F64F947EE4F">IPnpCallbackHardware2::OnReleaseHardware</a> method. The <b>OnReleaseHardware</b> method can then free resources that were allocated during the call to <b>OnPrepareHardware</b>. Because <b>OnReleaseHardware</b> must free resources for both success and failure cases of <b>OnPrepareHardware</b>, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.


## -remarks
The <b>IPnpCallbackHardware2::OnPrepareHardware</b> method differs from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a> method in that it receives raw and translated resources.

For information about parsing hardware resources, see <a href="wdf.finding_and_mapping_hardware_resources_in_a_umdf_driver">Finding and Mapping Hardware Resources in a UMDF Driver</a>.


See example code in <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware2.md">IPnpCallbackHardware2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardware2::OnPrepareHardware method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

