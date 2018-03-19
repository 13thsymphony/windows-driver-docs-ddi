---
UID: NE:wudfddi_types._WDF_PROPERTY_STORE_RETRIEVE_FLAGS
title: "_WDF_PROPERTY_STORE_RETRIEVE_FLAGS"
author: windows-driver-content
description: The WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration contains values that indicate whether UMDF should create a registry key if the key does not already exist.
old-location: wdf\wdf_property_store_retrieve_flags.htm
old-project: wdf
ms.assetid: bd64ef0d-b2e7-4f82-87a8-77fe98677fd9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_PROPERTY_STORE_RETRIEVE_FLAGS, WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration, WdfPropertyStoreCreateIfMissing, WdfPropertyStoreCreateVolatile, WdfPropertyStoreNormal, WdfPropertyStoreRetrieveFlagsMask, _WDF_PROPERTY_STORE_RETRIEVE_FLAGS, umdf.wdf_property_store_retrieve_flags, umdfstructs_c11a65c3-e37f-4adb-b480-1682d8e51700.xml, wdf.wdf_property_store_retrieve_flags, wudfddi_types/WDF_PROPERTY_STORE_RETRIEVE_FLAGS, wudfddi_types/WdfPropertyStoreCreateIfMissing, wudfddi_types/WdfPropertyStoreCreateVolatile, wudfddi_types/WdfPropertyStoreNormal, wudfddi_types/WdfPropertyStoreRetrieveFlagsMask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_PROPERTY_STORE_RETRIEVE_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_PROPERTY_STORE_RETRIEVE_FLAGS
req.product: Windows 10 or later.
---

# _WDF_PROPERTY_STORE_RETRIEVE_FLAGS Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration contains values that indicate whether  UMDF should create a registry key if the key does not already exist.

## Syntax
````
typedef enum _WDF_PROPERTY_STORE_RETRIEVE_FLAGS { 
  WdfPropertyStoreNormal              = 0,
  WdfPropertyStoreCreateIfMissing     = 0x1,
  WdfPropertyStoreCreateVolatile      = 0x2,
  WdfPropertyStoreRetrieveFlagsMask   = WdfPropertyStoreNormal |
                                      WdfPropertyStoreCreateIfMissing |
                                      WdfPropertyStoreCreateVolatile

} WDF_PROPERTY_STORE_RETRIEVE_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>WdfPropertyStoreNormal</td>
                    <td>Do not create the registry key if it does not exist.</td>
                </tr>
            
                <tr>
                    <td>WdfPropertyStoreCreateIfMissing</td>
                    <td>Create the registry key if it does not exist. The key will be <i>nonvolatile</i>, which means that it will not be deleted when Windows restarts.</td>
                </tr>
            
                <tr>
                    <td>WdfPropertyStoreCreateVolatile</td>
                    <td>Create the registry key if it does not exist. The key will be volatile, which means that it will be deleted when Windows restarts. This flag is available in UMDF versions 1.9 and later.</td>
                </tr>
            
                <tr>
                    <td>WdfPropertyStoreRetrieveFlagsMask</td>
                    <td>Reserved for system use.</td>
                </tr>
</table>

## Remarks

<b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration values are used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> methods.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>