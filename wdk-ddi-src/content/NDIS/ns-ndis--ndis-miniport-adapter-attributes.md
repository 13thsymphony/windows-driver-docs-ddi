---
UID: NS.ndis._NDIS_MINIPORT_ADAPTER_ATTRIBUTES
title: NDIS_MINIPORT_ADAPTER_ATTRIBUTES
author: windows-driver-content
description: The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures: NDIS_OBJECT_HEADER NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTESNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
old-location: netvista\ndis_miniport_adapter_attributes.htm
ms.assetid: 41e3c65a-0ab8-4f6f-af49-1aa2edbeda5c
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADAPTER_ATTRIBUTES
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
ms.keywords: NDIS_MINIPORT_ADAPTER_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_ATTRIBUTES
req.iface: 
---

# NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure



## -description
<p>The NDIS_MINIPORT_ADAPTER_ATTRIBUTES structure is a placeholder for the following structures:
  </p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</p>
<p>
<a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
     NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>
</p>


## -syntax

````
typedef union _NDIS_MINIPORT_ADAPTER_ATTRIBUTES {
  NDIS_OBJECT_HEADER                               Header;
  NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES AddDeviceRegistrationAttributes;
  NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES    RegistrationAttributes;
  NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES         GeneralAttributes;
  NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES         OffloadAttributes;
  NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES   Native_802_11_Attributes;
#if  (NDIS_SUPPORT_NDIS61)
  NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES HardwareAssistAttributes;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES             NDKAttributes;
#endif 
} NDIS_MINIPORT_ADAPTER_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_ATTRIBUTES;
````


## -struct-fields
<dl>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
     NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
     NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>
</p>
</dd>
</dl>

## -remarks
<p>Miniport drivers pass these structures to the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/5423d073-02a5-468b-b91e-713ac67a5253">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451558">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/9ce875fc-ed3f-43e9-bfbc-081f02cb1999">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8f0d539a-50c5-4ecd-b62d-6b32fe7cfaba">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7e8b5dbf-2d56-4278-8953-8e21ba1cee06">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_ATTRIBUTES union%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
