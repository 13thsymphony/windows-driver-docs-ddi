---
UID: NF:wudfddi.IWDFDevice3.MapIoSpace
title: IWDFDevice3::MapIoSpace method
author: windows-driver-content
description: The MapIoSpace method maps the given physical address range to system address space and returns a pseudo base address.
old-location: wdf\iwdfdevice3_mapiospace.htm
old-project: wdf
ms.assetid: 243C7299-7C74-408A-8FB9-32FB3315251F
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice3 interface, MapIoSpace method, MapIoSpace method, umdf.iwdfdevice3_mapiospace, MapIoSpace, MapIoSpace method, IWDFDevice3 interface, IWDFDevice3::\_MapIoSpace, wudfddi/IWDFDevice3::\_MapIoSpace, IWDFDevice3::MapIoSpace, IWDFDevice3, wdf.iwdfdevice3_mapiospace
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
-	IWDFDevice3.MapIoSpace
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# MapIoSpace method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>MapIoSpace</b> method maps the given physical address range to system address space and returns a pseudo base address.

## Syntax

````
HRESULT  MapIoSpace(
  [in]  PHYSICAL_ADDRESS    PhysicalAddress,
  [in]  SIZE_T              NumberOfBytes,
  [in]  MEMORY_CACHING_TYPE CacheType,
  [out] VOID                **pPseudoBaseAddress
);
````

## Parameters

`PhysicalAddress`

Specifies the starting 64-bit physical address of the I/O range to be mapped.

`NumberOfBytes`

Specifies a value greater than zero, indicating the number of bytes to be mapped.

`CacheType`

Specifies a <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range. The MEMORY_CACHING_TYPE enumeration type is defined in Wudfwdm.h.

`pPseudoBaseAddress`

The address of a location that receives a pointer to the pseudo base address.


## Return Value

The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

A driver must call this method during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MapIoSpace</b> maps the physical address returned in the resource list to a framework-managed address referred to as the pseudo base address.

 The driver can then use the pseudo base address to access device registers with READ_REGISTER_<i>Xxx</i> and WRITE_REGISTER_<i>Xxx</i> functions. For  an example, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

A driver that calls <b>MapIoSpace</b> must set the <b>UmdfDirectHardwareAccess</b> INF directive to <b>AllowDirectHardwareAccess</b>.

 If the driver sets the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>, calling <b>MapIoSpace</b> also maps the given physical address range to a user-mode base address range that the driver can subsequently access by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451219">GetHardwareRegisterMappedAddress</a>.

 For more information about  INF directives that UMDF drivers can use, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

The PHYSICAL_ADDRESS type is defined in Wudfwdm.h, as follows:<pre class="syntax" xml:space="preserve"><code>typedef LARGE_INTEGER PHYSICAL_ADDRESS;</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::MapIoSpace method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>