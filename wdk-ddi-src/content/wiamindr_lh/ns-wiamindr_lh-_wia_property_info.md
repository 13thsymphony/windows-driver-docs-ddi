---
UID: NS:wiamindr_lh._WIA_PROPERTY_INFO
title: "_WIA_PROPERTY_INFO"
author: windows-driver-content
description: The WIA_PROPERTY_INFO structure is used to store default access and valid value information for an item property of arbitrary type.
old-location: image\wia_property_info.htm
old-project: image
ms.assetid: 9ab9edb8-aa37-4c28-81c9-3e41751f14ed
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWIA_PROPERTY_INFO, PWIA_PROPERTY_INFO, PWIA_PROPERTY_INFO structure pointer [Imaging Devices], WIA_PROPERTY_INFO, WIA_PROPERTY_INFO structure [Imaging Devices], _WIA_PROPERTY_INFO, image.wia_property_info, wiamindr_lh/PWIA_PROPERTY_INFO, wiamindr_lh/WIA_PROPERTY_INFO, wiastrct_6e0091b3-43a3-473b-88e4-ec41533a5b0e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	wiamindr_lh.h
api_name:
-	WIA_PROPERTY_INFO
product: Windows
targetos: Windows
req.typenames: WIA_PROPERTY_INFO, *PWIA_PROPERTY_INFO
req.product: Windows 10 or later.
---

# _WIA_PROPERTY_INFO structure
The WIA_PROPERTY_INFO structure is used to store default access and valid value information for an item property of arbitrary type.

## Syntax
````
typedef struct _WIA_PROPERTY_INFO {
  ULONG   lAccessFlags;
  VARTYPE vt;
  union {
    struct {
      LONG Min;
      LONG Nom;
      LONG Max;
      LONG Inc;
    } Range;
    struct {
      DOUBLE Min;
      DOUBLE Nom;
      DOUBLE Max;
      DOUBLE Inc;
    } RangeFloat;
    struct {
      LONG cNumList;
      LONG Nom;
      BYTE *pList;
    } List;
    struct {
      LONG   cNumList;
      DOUBLE Nom;
      BYTE   *pList;
    } ListFloat;
    struct {
      LONG cNumList;
      GUID Nom;
      GUID *pList;
    } ListGuid;
    struct {
      LONG cNumList;
      BSTR Nom;
      BSTR *pList;
    } ListBStr;
    struct {
      LONG Nom;
      LONG ValidBits;
    } Flag;
    struct {
      LONG Dummy;
    } None;
  } ValidVal;
} WIA_PROPERTY_INFO, *PWIA_PROPERTY_INFO;
````

## Members


`lAccessFlags`

Specifies the access and property attribute flags for a property. See the Microsoft Windows SDK documentation for a list of WIA property attribute flags.

`ValidVal`



`vt`

Specifies the variant data type for the property. This member, which can be one of the following, controls which structure member of the <b>ValidValunion</b> is valid:

VT_UI1

VT_UI2

VT_UI4

VT_I2

VT_I4

VT_R4

VT_R8

VT_CLSID

VT_BSTR

See PROPVARIANT in the Windows SDK documentation for more information.

## Remarks
The WIA_PROPERTY_INFO is used by the minidriver to store information about a property of arbitrary type. This structure is also used by the <b>wiasSetItemPropAttribs</b> to set a property's valid values. The <b>lAccessFlags</b> member controls whether access to a property is read-only or read/write. This member also conveys information about the set of valid values for a property when they are defined by a list of values, a range of values, or a bitset of flags. The <b>vt</b> member contains information about the type of the property. Both members should be used to determine which member of the <b>ValidValunion</b> can be accessed. 

For example, for a read/write property of type <b>long</b>, whose valid values are integers in the range -128 to 127, and whose nominal value is 0, <b>lAccessFlags</b> would be set to WIA_PROP_RW | WIA_PROP_RANGE, and <b>vt</b> would be set to VT_I4. <b>Range.Min</b> would be set to -128, <b>Range.Max</b> would be set to 127, and <b>Range.Inc</b> would be set to 1. <b>Range.Nom</b> would be set to 0.

For a different property whose valid values are defined by a list of three GUID values, <b>lAccessFlags</b> would have its WIA_PROP_LIST bit set, and <b>vt</b> would be set to VT_CLSID. <b>ListGuid.cNumList</b> would be set to 3, and the three GUIDs are <b>ListGuid.pList</b>[0], <b>ListGuid.pList</b>[1], and <b>ListGuid.pList</b>[2].

A property whose valid values are defined by a bitset of the values 0x01, 0x02, 0x04, and 0x08 would have the WIA_PROP_FLAG bit set in <b>lAccessFlags</b>, and <b>vt</b> would be set to VT_UI4. For such a property, the value stored in <b>Flag.ValidBits</b> would be 0x0F, the bitwise OR of the four flag values previously mentioned.

The following examples show how to use array data with WIA_PROPERTY_INFO and how to call <a href="..\wiamdef\nf-wiamdef-wiaswritemultiple.md">wiasWriteMultiple</a> to set your property values.

Initialization might look like the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  // Initialize WIA_IPA_ITEM_TIME (NONE)
  g_pszItemDefaults[13]              = WIA_IPA_ITEM_TIME_STR;
  g_piItemDefaults [13]              = WIA_IPA_ITEM_TIME;
  g_pvItemDefaults [13].cai.celems   = MyNumberOfElements;
  g_pvItemDefaults [13].cai.pelems   = PointerToMyArray;
  g_pvItemDefaults [13].vt           = VT_VECTOR|VT_UI2; // MyArray is an array of DWORD values
  g_psItemDefaults [13].ulKind       = PRSPEC_PROPID;
  g_psItemDefaults [13].propid       = g_piItemDefaults [13];
  g_wpiItemDefaults[13].lAccessFlags = WIA_PROP_READ|WIA_PROP_NONE;
  g_wpiItemDefaults[13].vt           = g_pvItemDefaults [13].vt;</pre>
</td>
</tr>
</table></span></div>
At run time, changing the value with <b>wiasWriteMultiple</b> might look like the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  PROPVARIANT propVar;
  PROPSPEC    propSpec;
  PropVariantInit(&amp;propVar);
  propVar.vt          = VT_VECTOR | VT_UI2;
  propVar.caui.cElems = sizeof(SYSTEMTIME) / sizeof(WORD);
  propVar.caui.pElems = (WORD *) &amp;CurrentTimeStruct;
  propSpec.ulKind     = PRSPEC_PROPID;
  propSpec.propid     = WIA_IPA_ITEM_TIME;
  hr                  = wiasWriteMultiple(pWiasContext, 1, &amp;propSpec, &amp;propVar);</pre>
</td>
</tr>
</table></span></div>
<b>Note</b>  WIA uses the COM PROPVARIANT type, VARIANT (defined in the Microsoft Windows SDK documentation), so the default is VT_VECTOR, and not VT_ARRAY (which is also supported).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="..\wiamdef\nf-wiamdef-wiassetitempropattribs.md">wiasSetItemPropAttribs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIA_PROPERTY_INFO structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>