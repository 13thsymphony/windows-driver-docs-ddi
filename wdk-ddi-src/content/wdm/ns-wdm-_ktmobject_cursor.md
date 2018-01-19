---
UID : NS:wdm._KTMOBJECT_CURSOR
title : _KTMOBJECT_CURSOR
author : windows-driver-content
description : The KTMOBJECT_CURSOR structure receives enumeration information about KTM objects when a component calls ZwEnumerateTransactionObject.
old-location : kernel\ktmobject_cursor.htm
old-project : kernel
ms.assetid : 0cfcd019-0c5b-4635-859f-741a6e4aa91d
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _KTMOBJECT_CURSOR, KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KTMOBJECT_CURSOR
req.alt-loc : Wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR
req.product : Windows 10 or later.
---

# _KTMOBJECT_CURSOR structure
The <b>KTMOBJECT_CURSOR</b> structure receives enumeration information about KTM objects when a component calls <a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a>.

## Syntax
````
typedef struct _KTMOBJECT_CURSOR {
  GUID  LastQuery;
  ULONG ObjectIdCount;
  GUID  ObjectIds[1];
} KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR;
````

## Members

        
            `LastQuery`

            After <b>ZwEnumerateTransactionObject</b> returns, this member contains the GUID of the last object that <b>ZwEnumerateTransactionObject</b> enumerated. Before it calls <b>ZwEnumerateTransactionObject</b> the first time, the caller must set this value to zero.
        
            `ObjectIdCount`

            After <b>ZwEnumerateTransactionObject</b> returns, this member contains the number of GUIDs that the <b>ObjectIds</b> array contains.
        
            `ObjectIds`

            A caller-allocated array of GUID-typed elements. After <b>ZwEnumerateTransactionObject</b> returns, this array contains GUIDs that identify enumerated objects.

    ## Remarks
        The <b>KTMOBJECT_CURSOR</b> structure is used at the beginning of buffers that callers pass to the <b>ZwEnumerateTransactionObject</b> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KTMOBJECT_CURSOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>