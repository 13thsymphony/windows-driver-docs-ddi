---
UID : NS:d3dhal._DD_GETDRIVERINFO2DATA
title : _DD_GETDRIVERINFO2DATA
author : windows-driver-content
description : DirectX 8.0 and later versions only. DD_GETDRIVERINFO2DATA is passed in the lpvData member of the DD_GETDRIVERINFODATA structure when GUID_GetDriverInfo2 is specified in the guidInfo member of DD_GETDRIVERINFODATA in a DdGetDriverInfo call.
old-location : display\dd_getdriverinfo2data.htm
old-project : display
ms.assetid : f1b3e432-6972-49ff-9fce-b642c1be17ea
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DD_GETDRIVERINFO2DATA, DD_GETDRIVERINFO2DATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dhal.h
req.include-header : D3dhal.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DD_GETDRIVERINFO2DATA
req.alt-loc : d3dhal.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DD_GETDRIVERINFO2DATA
---

# _DD_GETDRIVERINFO2DATA structure
DirectX 8.0 and later versions only.
   

DD_GETDRIVERINFO2DATA is passed in the <b>lpvData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> structure when GUID_GetDriverInfo2 is specified in the <b>guidInfo</b> member of DD_GETDRIVERINFODATA in a <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a> call.

## Syntax
````
typedef struct _DD_GETDRIVERINFO2DATA {
  DWORD dwReserved;
  DWORD dwMagic;
  DWORD dwType;
  DWORD dwExpectedSize;
} DD_GETDRIVERINFO2DATA;
````

## Members

        
            `dwExpectedSize`

            Specifies the expected size, in bytes, of the information requested. Driver should only read (not write) this member.
        
            `dwMagic`

            Specifies the magic number. Has the value 
	  D3DGDI2_MAGIC if this is a 
	  <a href="https://msdn.microsoft.com/5e2dd363-9e72-4674-940e-8b4f06f6eb14">GetDriverInfo2</a> 
	  call. Otherwise this structure is, in fact, a 
	  <a href="https://msdn.microsoft.com/library/windows/hardware/ff551716">DD_STEREOMODE</a> 
	  call.
        
            `dwReserved`

            Specifies a reserved field. Driver should not read or write.
        
            `dwType`

            Specifies the type of information requested, which can contain one of the following D3DGDI2_TYPE_<i>Xxx</i> 
	values. Driver should only read (not write) this member.
	

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>D3DGDI2_TYPE_DEFER_AGP_FREES</td>
<td>
<b>NT-based operating systems only.</b>

Is used to notify the driver that it should properly 
		handle the destruction of <a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP memory</a> for surfaces. 
		The runtime provides a pointer to a 
		<a href="..\d3dhal\ns-d3dhal-_dd_free_deferred_agp_data.md">DD_FREE_DEFERRED_AGP_DATA</a> 
		structure in the <b>lpvData</b> field of the DD_GETDRIVERINFODATA data structure.

The driver sometimes receives this notification before a display mode change occurs. The runtime 
		only sends this notification if it is to be used to perform the display mode change. Drivers should check 
		the process identifier (PID) of the process destroying the surface against the process that created the 
		surface. If the PIDs are different, the driver probably should not destroy the user-mode mappings of the 
		AGP memory because an application might still be using the memory.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_DEFERRED_AGP_AWARE</td>
<td>
<b>NT-based operating systems only.</b>

Is used to inform the driver that the runtime sends 
		D3DGDI2_TYPE_FREE_DEFERRED_AGP and D3DGDI2_TYPE_DEFER_AGP_FREES notifications at the appropriate time 
		(such as, after the last outstanding <a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP memory</a> 
		lock is released). The runtime provides a pointer to a 
		<a href="..\d3dhal\ns-d3dhal-_dd_deferred_agp_aware_data.md">DD_DEFERRED_AGP_AWARE_DATA</a> 
		structure in the 
		<b>lpvData</b> field 
		of the DD_GETDRIVERINFODATA data structure.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_DXVERSION</td>
<td>
Is used to notify the driver of the current DX runtime version 
		being used by the application. The runtime provides a pointer to a 
		<a href="..\d3dhal\ns-d3dhal-_dd_dxversion.md">DD_DXVERSION</a> structure in the <b>lpvData</b> 
		field of the DD_GETDRIVERINFODATA data structure.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_FREE_DEFERRED_AGP</td>
<td>
<b>NT-based operating systems only.</b>

Is used to notify the driver that it is now safe 
		to destroy all the user-mode mappings of the 
		<a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP memory</a>. The driver preserved these user-mode 
		mappings when surfaces were destroyed and it received a D3DGDI2_TYPE_DEFER_AGP_FREES notification. The 
		runtime provides a pointer to a 
		<a href="..\d3dhal\ns-d3dhal-_dd_free_deferred_agp_data.md">DD_FREE_DEFERRED_AGP_DATA</a> 
		structure in the <b>lpvData</b> field of the DD_GETDRIVERINFODATA data structure.

The driver receives 
		this notification when all display devices within the process stop using surfaces, textures, vertex 
		buffers, and index buffers that were locked at the time of the display mode change. 

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETADAPTERGROUP</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to query the driver for the identity of 
		the group of adapters that are part of its 
		multiple-head video card. This group shares video 
		hardware 
		like video memory and the 3D accelerator. The 
		driver should set the data structure pointed to by 
		the <b>lpvData</b> field of the 
		DD_GETDRIVERINFODATA data structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_getadaptergroupdata.md">DD_GETADAPTERGROUPDATA</a>.
		

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETD3DCAPS8</td>
<td>
This type indicates that the runtime requests to receive a 
		D3DCAPS8 structure giving the DirectX 8.0 style capabilities of the device. The driver should copy an 
		initialized D3DCAPS8 structure into the <b>lpvData</b> field of the DD_GETDRIVERINFODATA structure.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETD3DCAPS9</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

<b>Required for DirectX 9.0 and later drivers.</b>

This type indicates that the runtime requests to 
		receive a D3DCAPS9 structure giving the 
		DirectX 9.0 style capabilities of the device. The 
		driver should copy an initialized D3DCAPS9 
		structure 
		into the <b>lpvData</b> field 
		of the DD_GETDRIVERINFODATA structure.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETD3DQUERY</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to query 
		the driver for information about a particular query 
		type that it supports. The driver should set the 
		data 
		structure pointed to by the 
		<b>lpvData</b> 
		field of 
		the DD_GETDRIVERINFODATA data structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_getd3dquerydata.md">DD_GETD3DQUERYDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETD3DQUERYCOUNT</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to 
		query the driver for the number of query types that it 
		supports. The driver should set the data structure 
		pointed to by the <b>lpvData</b> field of the 
		DD_GETDRIVERINFODATA data structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_getd3dquerycountdata.md">DD_GETD3DQUERYCOUNTDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETDDIVERSION</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to 
		query the driver for the version of the DDI that 
		the driver supports; this DDI version, in turn, 
		depends 
		on the version of DirectX that makes this request. 
		The driver should set the <b>dwDDIVersion</b> 
		member 
		of the <a href="..\d3dhal\ns-d3dhal-_dd_getddiversiondata.md">DD_GETDDIVERSIONDATA</a> 
		structure, 
		which the <b>lpvData</b> field of the 
		DD_GETDRIVERINFODATA data structure points to, to 
		the appropriate 
		DDI version.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETEXTENDEDMODE</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to 
		query the driver for information about a particular 
		extended display mode that it supports. The driver 
		should set the data structure pointed to by the 
		<b>lpvData</b> field of the DD_GETDRIVERINFODATA 
		data 
		structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_getextendedmodedata.md">DD_GETEXTENDEDMODEDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETEXTENDEDMODECOUNT</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used 
		to query the driver for the number of extended 
		display modes that it supports. The driver should 
		set the 
		data structure pointed to by the <b>lpvData</b> 
		field of the DD_GETDRIVERINFODATA data structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_getextendedmodecountdata.md">DD_GETEXTENDEDMODECOUNTDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETFORMAT</td>
<td>
Is used to query for a particular surface format from the driver. 
		The data structure pointed to by the <b>lpvData</b> 
		field of the DD_GETDRIVERINFODATA data structure is 
		<a href="..\d3dhal\ns-d3dhal-_dd_getformatdata.md">DD_GETFORMATDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETFORMATCOUNT</td>
<td>
Is used to request the number of DirectX 8.0 and
		later style surface formats supported by the 
		driver. The data structure pointed to by the 
		<b>lpvData</b> 
		field of the DD_GETDRIVERINFODATA is 
		<a href="..\d3dhal\ns-d3dhal-_dd_getformatcountdata.md">DD_GETFORMATCOUNTDATA</a>.

</td>
</tr>
<tr>
<td>D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS</td>
<td>
<b>DirectX 9.0 and later versions only.</b>

Is used to query the driver for the number of 
		multiple-sample quality levels for a given 
		render-target format that it supports. Whether the 
		display device supports maskable or submaskable 
		multisampling, the driver for the device must provide 
		the number of quality levels for the 
		D3DMULTISAMPLE_NONMASKABLE multiple-sample type. The 
		driver should set the data structure pointed to by 
		the <b>lpvData</b> 
		field of the DD_GETDRIVERINFODATA 
		data structure to 
		<a href="..\d3dhal\ns-d3dhal-_dd_multisamplequalitylevelsdata.md">DD_MULTISAMPLEQUALITYLEVELSDATA</a>.

</td>
</tr>
</table>

    ## Remarks
        The <b>dwExpectedSize</b> member of the DD_GETDRIVERINFODATA structure is not used when a <a href="https://msdn.microsoft.com/5e2dd363-9e72-4674-940e-8b4f06f6eb14">GetDriverInfo2</a> request is being made. Its value is undefined in this case and should be ignored. Instead, the actual expected size of the data is found in the <b>dwExpectedSize</b> member of DD_GETDRIVERINFO2DATA.

The following code fragment demonstrates how to handle <a href="https://msdn.microsoft.com/5e2dd363-9e72-4674-940e-8b4f06f6eb14">GetDriverInfo2</a>:

For more information about D3DCAPS8 and D3DCAPS9, see the DirectX SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_deferred_agp_aware_data.md">DD_DEFERRED_AGP_AWARE_DATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_dxversion.md">DD_DXVERSION</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_free_deferred_agp_data.md">DD_FREE_DEFERRED_AGP_DATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getadaptergroupdata.md">DD_GETADAPTERGROUPDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getd3dquerycountdata.md">DD_GETD3DQUERYCOUNTDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getd3dquerydata.md">DD_GETD3DQUERYDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getddiversiondata.md">DD_GETDDIVERSIONDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getextendedmodecountdata.md">DD_GETEXTENDEDMODECOUNTDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getextendedmodedata.md">DD_GETEXTENDEDMODEDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getformatcountdata.md">DD_GETFORMATCOUNTDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getformatdata.md">DD_GETFORMATDATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_multisamplequalitylevelsdata.md">DD_MULTISAMPLEQUALITYLEVELSDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551716">DD_STEREOMODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETDRIVERINFO2DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>