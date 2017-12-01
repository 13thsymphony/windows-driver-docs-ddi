---
UID: NE.ntddndis._NDIS_SWITCH_PORT_PROPERTY_TYPE
title: NDIS_SWITCH_PORT_PROPERTY_TYPE
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.
old-location: netvista\ndis_switch_port_property_type.htm
old-project: netvista
ms.assetid: c70137b2-1926-4d45-a473-8eb7195ba23d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: GET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT, *PGET_CONFIGURATION_IOCTL_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_PORT_PROPERTY_TYPE
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration



## -description
<p>The <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.</p>


## -syntax

````
typedef enum _NDIS_SWITCH_PORT_PROPERTY_TYPE { 
  NdisSwitchPortPropertyTypeUndefined,
  NdisSwitchPortPropertyTypeCustom,
  NdisSwitchPortPropertyTypeSecurity,
  NdisSwitchPortPropertyTypeVlan,
  NdisSwitchPortPropertyTypeProfile,
  NdisSwitchPortPropertyTypeIsolation,
  NdisSwitchPortPropertyTypeRoutingDomain,
  NdisSwitchPortPropertyTypeMaximum
} NDIS_SWITCH_PORT_PROPERTY_TYPE, *PNDIS_SWITCH_PORT_PROPERTY_TYPE;
````


## -enum-fields
<dl>

### -field <a id="NdisSwitchPortPropertyTypeUndefined"></a><a id="ndisswitchportpropertytypeundefined"></a><a id="NDISSWITCHPORTPROPERTYTYPEUNDEFINED"></a><b>NdisSwitchPortPropertyTypeUndefined</b>

<dd>
<p>The port property type is not defined.</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeCustom"></a><a id="ndisswitchportpropertytypecustom"></a><a id="NDISSWITCHPORTPROPERTYTYPECUSTOM"></a><b>NdisSwitchPortPropertyTypeCustom</b>

<dd>
<p>This value specifies a custom port property that is defined  by an independent software vendor (ISV). Custom port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-custom.md">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a> structure.</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeSecurity"></a><a id="ndisswitchportpropertytypesecurity"></a><a id="NDISSWITCHPORTPROPERTYTYPESECURITY"></a><b>NdisSwitchPortPropertyTypeSecurity</b>

<dd>
<p>This value specifies a security port property. Security port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-security.md">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a> structure.</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeVlan"></a><a id="ndisswitchportpropertytypevlan"></a><a id="NDISSWITCHPORTPROPERTYTYPEVLAN"></a><b>NdisSwitchPortPropertyTypeVlan</b>

<dd>
<p>This value specifies a virtual local area network (VLAN) port property. VLAN port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure.</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeProfile"></a><a id="ndisswitchportpropertytypeprofile"></a><a id="NDISSWITCHPORTPROPERTYTYPEPROFILE"></a><b>NdisSwitchPortPropertyTypeProfile</b>

<dd>
<p>This value specifies a profile port property. Profile port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-profile.md">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a> structure.</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeIsolation"></a><a id="ndisswitchportpropertytypeisolation"></a><a id="NDISSWITCHPORTPROPERTYTYPEISOLATION"></a><b>NdisSwitchPortPropertyTypeIsolation</b>

<dd>
<p>This value specifies an isolation port property. Isolation port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-isolation.md">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>
</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeRoutingDomain"></a><a id="ndisswitchportpropertytyperoutingdomain"></a><a id="NDISSWITCHPORTPROPERTYTYPEROUTINGDOMAIN"></a><b>NdisSwitchPortPropertyTypeRoutingDomain</b>

<dd>
<p>This value specifies a routing domain port property. Routing domain port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-routing-domain.md">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>
</p>
</dd>

### -field <a id="NdisSwitchPortPropertyTypeMaximum"></a><a id="ndisswitchportpropertytypemaximum"></a><a id="NDISSWITCHPORTPROPERTYTYPEMAXIMUM"></a><b>NdisSwitchPortPropertyTypeMaximum</b>

<dd>
<p>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.

</p>
</dd>
</dl>

## -remarks
<p>The <b>PropertyType</b> member of the following structures is an <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration data type: 

</p>

<p>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-delete-parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>
</p>

<p>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-feature-status-parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>
</p>

<p>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-enum-parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>
</p>

<p>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>
</p>

<p>For more information about extensible switch port policies, see <a href="NULL">Hyper-V Extensible Switch Policies</a>.

</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-feature-status-parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-custom.md">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-delete-parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-enum-parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-profile.md">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-security.md">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-switch-port-property-vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
