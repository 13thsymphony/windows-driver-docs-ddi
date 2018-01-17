---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNamedValue
title: IWDFNamedPropertyStore::GetNamedValue method
author: windows-driver-content
description: The GetNamedValue method retrieves the value of a property.
old-location: wdf\iwdfnamedpropertystore_getnamedvalue.htm
old-project: wdf
ms.assetid: 9581e3af-f7f8-4365-8bb2-daedcb7a3280
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFNamedPropertyStore, IWDFNamedPropertyStore::GetNamedValue, GetNamedValue
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
req.alt-api: IWDFNamedPropertyStore.GetNamedValue
req.alt-loc: WUDFx.dll
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFNamedPropertyStore::GetNamedValue method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNamedValue</b> method retrieves the value of a property.



## -syntax

````
HRESULT GetNamedValue(
  [in]  LPCWSTR     pszName,
  [out] PROPVARIANT *pv
);
````


## -parameters

### -param pszName [in]

A pointer to a null-terminated string that contains the name of the property.


### -param pv [out]

A pointer to a variable that receives the value for the property. 


## -returns
<b>GetNamedValue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
The <b>GetNamedValue</b> method allocates memory for a string in the <a href="https://msdn.microsoft.com/e86cc279-826d-4767-8d96-fc8280060ea1">PROPVARIANT</a> structure pointed to by the <i>pv</i> parameter.   The caller must then free this memory by calling the <a href="https://msdn.microsoft.com/062b6065-a56f-4ecd-b232-3ba338a6d806">PropVariantClear</a> function, as shown in the following snippet:

If the caller does not free the memory, a memory leak may result.

The following variant types are supported for property values. The following table shows the variant type that is returned regardless of the original variant type.

VT_BSTR

While clients read a string value, the value is returned as VT_LPWSTR regardless of the original variant type that was used to write the value.

VT_LPWSTR

VT_LPSTR

VT_I1

While clients read an integer value, the value is returned as VT_UI4 regardless of the original variant type that was used to write the value.

VT_UI1

VT_I2

VT_UI2

VT_I4

VT_UI4

VT_UINT

VT_BLOB

The binary value is returned as VT_BLOB.

VT_VECTOR | VT_LPWSTR

The string array is returned as VT_VECTOR | VT_LPWSTR

A string that contains environment variables is expanded on read.

For more information, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/062b6065-a56f-4ecd-b232-3ba338a6d806">PropVariantClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e86cc279-826d-4767-8d96-fc8280060ea1">PROPVARIANT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFNamedPropertyStore::GetNamedValue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

