---
UID: NE:ntddndis._NDIS_SWITCH_PROPERTY_TYPE
title: "_NDIS_SWITCH_PROPERTY_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_TYPE enumeration specifies the type of policy property for a Hyper-V extensible switch.
old-location: netvista\ndis_switch_property_type.htm
old-project: netvista
ms.assetid: baa1b837-6f9b-41f4-acf8-e640f8e9f8da
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_SWITCH_PROPERTY_TYPE, NDIS_SWITCH_PROPERTY_TYPE, NDIS_SWITCH_PROPERTY_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPropertyTypeCustom, NdisSwitchPropertyTypeMaximum, NdisSwitchPropertyTypeUndefined, PNDIS_SWITCH_PROPERTY_TYPE, PNDIS_SWITCH_PROPERTY_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PROPERTY_TYPE, netvista.ndis_switch_property_type, ntddndis/NDIS_SWITCH_PROPERTY_TYPE, ntddndis/NdisSwitchPropertyTypeCustom, ntddndis/NdisSwitchPropertyTypeMaximum, ntddndis/NdisSwitchPropertyTypeUndefined, ntddndis/PNDIS_SWITCH_PROPERTY_TYPE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PROPERTY_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PROPERTY_TYPE, *PNDIS_SWITCH_PROPERTY_TYPE
---

# _NDIS_SWITCH_PROPERTY_TYPE Enumeration
The <b>NDIS_SWITCH_PROPERTY_TYPE</b> enumeration specifies the type of policy property for a Hyper-V extensible switch.

## Syntax
````
typedef enum _NDIS_SWITCH_PROPERTY_TYPE { 
  NdisSwitchPropertyTypeUndefined,
  NdisSwitchPropertyTypeCustom,
  NdisSwitchPropertyTypeMaximum
} NDIS_SWITCH_PROPERTY_TYPE, *PNDIS_SWITCH_PROPERTY_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisSwitchPropertyTypeCustom</td>
                    <td>This value specifies a custom switch property that is defined  by an independent software vendor (ISV).</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPropertyTypeMaximum</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPropertyTypeUndefined</td>
                    <td>The switch property type is not defined.</td>
                </tr>
</table>

## Remarks

The <b>PropertyType</b> member of the following structures is an <b>NDIS_SWITCH_PROPERTY_TYPE</b> enumeration data type: 



<ul>
<li>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_delete_parameters.md">NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</a>


</li>
<li>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_enum_parameters.md">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a>


</li>
<li>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_parameters.md">NDIS_SWITCH_PROPERTY_PARAMETERS</a>


</li>
</ul>
For more information about extensible switch  policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_parameters.md">NDIS_SWITCH_PROPERTY_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_enum_parameters.md">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_delete_parameters.md">NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PROPERTY_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>