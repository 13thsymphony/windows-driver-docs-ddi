---
UID: NF.wiamdef.wiasParseEndorserString
title: wiasParseEndorserString
author: windows-driver-content
description: The wiasParseEndorserString function parses an endorser string, replacing WIA service-defined and vendor-defined tokens in the string with values associated with those tokens.
old-location: image\wiasparseendorserstring.htm
old-project: image
ms.assetid: c724a4f5-55ef-413d-bd1a-9cd39d3e42f5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: wiasParseEndorserString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiasParseEndorserString
req.alt-loc: Wiaservc.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# wiasParseEndorserString function



## -description
<p>The <b>wiasParseEndorserString</b> function parses an endorser string, replacing WIA service-defined and vendor-defined tokens in the string with values associated with those tokens.</p>


## -syntax

````
HRESULT _stdcall wiasParseEndorserString(
  _In_      BYTE               *pWiasContext,
            LONG               lFlags,
  _Out_opt_ WIAS_ENDORSER_INFO *pInfo,
  _Out_     BSTR               *pOutputString
);
````


## -parameters
<dl>

### -param pWiasContext [in]

<dd>
<p>Pointer to a WIA Item context (the context of the item containing the WIA_DPS_ENDORSER_STRING property (described in the Microsoft Windows SDK documentation)).</p>
</dd>

### -param lFlags 

<dd>
<p>Reserved for system use and should be set to 0.</p>
</dd>

### -param pInfo [out, optional]

<dd>
<p>Pointer to a <a href="..\wiamindr_lh\ns-wiamindr-lh--wias-endorser-info.md">WIAS_ENDORSER_INFO</a> structure containing the page count and a list of custom token/value pairs. Can be <b>NULL</b>.</p>
</dd>

### -param pOutputString [out]

<dd>
<p>Pointer to a memory location that receives the address of the parsed endorser string. If *<i>pOutputString</i> is non-<b>NULL</b> on entry, then the function assumes that the caller allocated the buffer; otherwise the WIA service will allocate it. Note that the WIA service assumes the <i>maximum</i> resultant endorser string is MAX_PATH (defined in <i>stdlib.h</i>) characters long. If the driver expects the string to be longer, it should allocate the buffer itself. If the caller allocates the buffer, it <i>must</i> initialize the contents of the buffer to zero before using this function.</p>
</dd>
</dl>

## -returns
<p>On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).</p>

## -remarks
<p>An application sets the WIA_DPS_ENDORSER_STRING property to a string that can contain the WIA service-defined tokens $DATE$, $TIME$, $PAGE_COUNT$, $DAY$, $MONTH$, and $YEAR$, as well as vendor-defined tokens. After a driver calls <b>wiasParseEndorserString</b>, the string pointed to by <i>pOutputString</i> contains a copy of the string in WIA_DPS_ENDORSER_STRING property, but with any tokens replaced by the values the tokens represent. For example, if the application set the endorser string to "This page was scanned on $DATE$", and the current date was October 1, 2000, the resulting output string would be "This page was scanned on 2000/10/1".</p>

<p>The list of standard WIA endorser tokens can be found in <i>wiadef.h</i>.</p>

<p>Drivers can request that <b>wiasParseEndorserString</b> substitute values for vendor-defined tokens by filling out a <a href="..\wiamindr_lh\ns-wiamindr-lh--wias-endorser-value.md">WIAS_ENDORSER_VALUE</a> structure for each token/value pair, and packaging all of these structures in a <a href="..\wiamindr_lh\ns-wiamindr-lh--wias-endorser-info.md">WIAS_ENDORSER_INFO</a> structure. The following example shows how this function can be used.</p>

<p>Assuming that the WIA_DPS_ENDORSER_STRING property contains "This is $MY_TOKEN$", and that the call to <b>wiasParseEndorserString</b> was successful, <i>bstrResultingEndorser</i> will now contain "This is My value".</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wiamdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wiaservc.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Wiaservc.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wiamindr_lh\ns-wiamindr-lh--wias-endorser-info.md">WIAS_ENDORSER_INFO</a>
</dt>
<dt>
<a href="..\wiamindr_lh\ns-wiamindr-lh--wias-endorser-value.md">WIAS_ENDORSER_VALUE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasParseEndorserString function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
