---
UID: NS:ndis._NDIS_CONFIGURATION_OBJECT
title: _NDIS_CONFIGURATION_OBJECT
author: windows-driver-content
description: The NDIS_CONFIGURATION_OBJECT structure defines the attributes of a configuration object that an NDIS driver can pass to the NdisOpenConfigurationEx function.
old-location: netvista\ndis_configuration_object.htm
old-project: netvista
ms.assetid: 8fa80414-c87a-4f05-b99c-5153f08a0862
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_CONFIGURATION_OBJECT, *PNDIS_CONFIGURATION_OBJECT, NDIS_CONFIGURATION_OBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_CONFIGURATION_OBJECT
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
req.typenames: *PNDIS_CONFIGURATION_OBJECT, NDIS_CONFIGURATION_OBJECT
---

# _NDIS_CONFIGURATION_OBJECT structure



## -description
The NDIS_CONFIGURATION_OBJECT structure defines the attributes of a configuration object that an NDIS
  driver can pass to the 
  <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">
  NdisOpenConfigurationEx</a> function.



## -syntax

````
typedef struct _NDIS_CONFIGURATION_OBJECT {
  NDIS_OBJECT_HEADER Header;
  NDIS_HANDLE        NdisHandle;
  ULONG              Flags;
} NDIS_CONFIGURATION_OBJECT, *PNDIS_CONFIGURATION_OBJECT;
````


## -struct-fields

### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_CONFIGURATION_OBJECT structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CONFIGURATION_OBJECT, the 
     <b>Revision</b> member to NDIS_CONFIGURATION_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CONFIGURATION_OBJECT_REVISION_1.


### -field NdisHandle

An NDIS handle that the caller obtained during initialization.


### -field Flags

A bitwise OR of the following flags:
     




### -field NDIS_CONFIG_FLAG_FILTER_INSTANCE_CONFIGURATION

Set this flag if a monitoring filter driver must access the filter module configuration for a
       specific filter module when there are multiple filter modules configured over the same miniport
       adapter. Modifying filter drivers must not use this flag.

</dd>
</dl>

## -remarks
To configuration parameters in the registry, an NDIS driver can use the NDIS_CONFIGURATION_OBJECT
    structure to define a configuration object and then call the 
    <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a> function
    to get a configuration handle.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CONFIGURATION_OBJECT structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

