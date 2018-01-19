---
UID : NN:wudfddi.IWDFUnifiedPropertyStore
title : IWDFUnifiedPropertyStore
author : windows-driver-content
description : The IWDFUnifiedPropertyStore interface exposes a unified property store.
old-location : wdf\iwdfunifiedpropertystore.htm
old-project : wdf
ms.assetid : F039450D-3B66-4891-9078-7058E889C2F0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.alt-api : IWDFUnifiedPropertyStore
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---

# IWDFUnifiedPropertyStore interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUnifiedPropertyStore</b> interface exposes a unified property store.

## Methods

<p>The <b>IWDFUnifiedPropertyStore</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFUnifiedPropertyStore.GetPropertyData](nf-wudfddi-iwdfunifiedpropertystore-getpropertydata.md) | The GetPropertyData method retrieves the current setting for a device property. |
| [wudfddi.IWDFUnifiedPropertyStore.SetPropertyData](nf-wudfddi-iwdfunifiedpropertystore-setpropertydata.md) | The SetPropertyData method modifies the current setting of a device property. |

## Remarks

Drivers can use the  <b>IWDFUnifiedPropertyStore</b> interface to access device properties that are defined as part of the unified device property model.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **DLL** | WUDFx.dll |

    ## See Also

        <dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystorefactory.md">IWDFUnifiedPropertyStoreFactory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStore interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>