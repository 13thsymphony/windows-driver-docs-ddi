---
UID : NN:wudfddi.IWDFUnifiedPropertyStoreFactory
title : IWDFUnifiedPropertyStoreFactory
author : windows-driver-content
description : The IWDFUnifiedPropertyStoreFactory interface is a factory interface that is used to create a unified property store interface.
old-location : wdf\iwdfunifiedpropertystorefactory.htm
old-project : wdf
ms.assetid : 34884B88-187A-4079-843D-F777287442F7
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
req.alt-api : IWDFUnifiedPropertyStoreFactory
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

# IWDFUnifiedPropertyStoreFactory interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUnifiedPropertyStoreFactory</b> interface is a factory interface that is used to create a unified property store interface.

## Methods

<p>The <b>IWDFUnifiedPropertyStoreFactory</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore](nf-wudfddi-iwdfunifiedpropertystorefactory-retrieveunifieddevicepropertystore.md) | The RetrieveUnifiedDevicePropertyStore method retrieves a unified property store interface. |

## Remarks

A unified property store interface is exposed only from the device object. To retrieve this interface, the driver can call <b>IWDFDevice::QueryInterface</b> or <b>IWDFDeviceInitialize::QueryInterface</b>. If required, the driver can then access the properties before creating the device.

For related information, see <a href="https://msdn.microsoft.com/51105f84-38d8-4005-a3fd-4beccc0a2a39">Unified Device Property Model</a>.

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
<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStoreFactory interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>