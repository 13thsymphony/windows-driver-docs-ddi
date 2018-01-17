---
UID: NF:wudfddi.IWDFNamedPropertyStore.SetNamedValue
title: IWDFNamedPropertyStore::SetNamedValue method
author: windows-driver-content
description: The SetNamedValue method sets the value of a property.
old-location: wdf\iwdfnamedpropertystore_setnamedvalue.htm
old-project: wdf
ms.assetid: 1fd075c9-7d0e-4670-bac0-b7b8ba0a714f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFNamedPropertyStore, IWDFNamedPropertyStore::SetNamedValue, SetNamedValue
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
req.alt-api: IWDFNamedPropertyStore.SetNamedValue
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

# IWDFNamedPropertyStore::SetNamedValue method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetNamedValue</b> method sets the value of a property.



## -syntax

````
HRESULT SetNamedValue(
  [in]       LPCWSTR     pszName,
  [in] const PROPVARIANT *pv
);
````


## -parameters

### -param pszName [in]

A pointer to a null-terminated string that contains the name of the property.


### -param pv [in]

A pointer to the value that the property is set to. 


## -returns
<b>SetNamedValue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
The following variant types are supported for property values. The following table shows the types of values that the framework writes for particular variant types.

VT_BSTR

Writes a string value.

VT_LPWSTR

VT_LPSTR

VT_I1

Writes an integer value.

VT_UI1

VT_I2

VT_UI2

VT_I4

VT_UI4

VT_UINT

VT_BLOB

Writes a binary value.

VT_VECTOR | VT_LPWSTR

Writes a string array.

For more information, see <a href="wdf.using_the_registry_in_umdf_drivers">Using the Registry in UMDF-based Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFNamedPropertyStore::SetNamedValue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

