---
UID : NE:ntddndis._NDIS_SWITCH_FEATURE_STATUS_TYPE
title : "_NDIS_SWITCH_FEATURE_STATUS_TYPE"
author : windows-driver-content
description : The NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a custom policy property, or feature, of a Hyper-V extensible switch.
old-location : netvista\ndis_switch_feature_status_type.htm
old-project : netvista
ms.assetid : a3255313-1d49-4286-a48a-6a1729ccf7fe
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration [Network Drivers Starting with Windows Vista], ntddndis/NdisSwitchFeatureStatusTypeCustom, ntddndis/PNDIS_SWITCH_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_FEATURE_STATUS_TYPE, _NDIS_SWITCH_FEATURE_STATUS_TYPE, ntddndis/NdisSwitchFeatureStatusTypeUndefined, NdisSwitchFeatureStatusTypeUndefined, NDIS_SWITCH_FEATURE_STATUS_TYPE, netvista.ndis_switch_feature_status_type, PNDIS_SWITCH_FEATURE_STATUS_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], NdisSwitchFeatureStatusTypeCustom, ntddndis/NdisSwitchFeatureStatusTypeMaximum, PNDIS_SWITCH_FEATURE_STATUS_TYPE, NdisSwitchFeatureStatusTypeMaximum, ntddndis/NDIS_SWITCH_FEATURE_STATUS_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SWITCH_FEATURE_STATUS_TYPE, NDIS_SWITCH_FEATURE_STATUS_TYPE"
---

# _NDIS_SWITCH_FEATURE_STATUS_TYPE Enumeration
The <b>NDIS_SWITCH_FEATURE_STATUS_TYPE</b> enumeration specifies the type of status information for a custom policy property, or <i>feature</i>, of a Hyper-V extensible switch.

An extensible switch feature is defined and supported by an independent software vendor (ISV).

## Syntax
````
typedef enum _NDIS_SWITCH_FEATURE_STATUS_TYPE { 
  NdisSwitchFeatureStatusTypeUndefined,
  NdisSwitchFeatureStatusTypeCustom,
  NdisSwitchFeatureStatusTypeMaximum
} NDIS_SWITCH_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_FEATURE_STATUS_TYPE;
````

## Constants

<table>

<tr>
<td>NdisSwitchFeatureStatusTypeCustom</td>
<td>The feature status information is for a custom extensible switch feature that is provided by an ISV.</td>
</tr>

<tr>
<td>NdisSwitchFeatureStatusTypeMaximum</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.</td>
</tr>

<tr>
<td>NdisSwitchFeatureStatusTypeUndefined</td>
<td>The feature status information is not defined.</td>
</tr>
</table>

## Remarks

The <b>FeatureStatusType</b> member of the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_parameters.md">NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</a> structure is an <a href="..\ntddndis\ne-ntddndis-_ndis_switch_property_type.md">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration data type.

For more information about extensible switch  policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_parameters.md">NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>