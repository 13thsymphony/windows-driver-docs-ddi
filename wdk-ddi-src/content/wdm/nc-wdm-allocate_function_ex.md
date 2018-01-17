---
UID: NC:wdm.ALLOCATE_FUNCTION_EX
title: ALLOCATE_FUNCTION_EX function
author: windows-driver-content
description: The LookasideListAllocateEx routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty.
old-location: kernel\lookasidelistallocateex.htm
old-project: kernel
ms.assetid: 4c9df63e-b0cb-4a49-9a01-9fc8f8c592f6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ALLOCATE_FUNCTION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LookasideListAllocateEx
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.typenames: *PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# ALLOCATE_FUNCTION_EX function



## -description
The <i>LookasideListAllocateEx</i> routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty.



## -syntax

````
ALLOCATE_FUNCTION_EX LookasideListAllocateEx;

PVOID LookasideListAllocateEx(
  _In_    POOL_TYPE          PoolType,
  _In_    SIZE_T             NumberOfBytes,
  _In_    ULONG              Tag,
  _Inout_ PLOOKASIDE_LIST_EX Lookaside
)
{ ... }
````


## -parameters

### -param PoolType [in]

Specifies the type of storage to allocate for the new lookaside-list entry. The caller sets this parameter to a valid <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration value, and possibly bitwise ORs this value with one of the following flag bits:

<ul>
<li>POOL_RAISE_IF_ALLOCATION_FAILURE</li>
<li>POOL_QUOTA_FAIL_INSTEAD_OF_RAISE</li>
</ul>
For more information about the POOL_RAISE_IF_ALLOCATION_FAILURE flag, see <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. For more information about the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag, see <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>.

If, in the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> call that initialized the lookaside list, the <i>Flags</i> parameter is zero, the <i>PoolType</i> parameter that the <i>LookasideListAllocateEx</i> routine receives is the same <i>PoolType</i> parameter value that was passed to <b>ExInitializeLookasideListEx</b>.

If, in the <b>ExInitializeLookasideListEx</b> call, <i>Flags</i> = EX_LOOKASIDE_LIST_EX_FLAGS_RAISE_ON_FAIL, the <i>PoolType</i> parameter that the <i>LookasideListAllocateEx</i> routine receives is the bitwise OR of POOL_RAISE_IF_ALLOCATION_FAILURE and the <i>PoolType</i> parameter value that was passed to <b>ExInitializeLookasideListEx</b>. The <i>LookasideListAllocateEx</i> routine can pass its <i>PoolType</i> parameter value, without modification, to the <b>ExAllocatePoolWithTag</b> routine. 

If, in the <b>ExInitializeLookasideListEx</b> call, Flags = EX_LOOKASIDE_LIST_EX_FLAGS_FAIL_NO_RAISE, the <i>PoolType</i> parameter that the <i>LookasideListAllocateEx</i> routine receives is the bitwise OR of POOL_QUOTA_FAIL_INSTEAD_OF_RAISE and the <i>PoolType</i> value that was passed to <b>ExInitializeLookasideListEx</b>.  The <i>LookasideListAllocateEx</i> routine can pass its <i>PoolType</i> parameter value, without modification, to the <b>ExAllocatePoolWithQuotaTag</b> routine.


### -param NumberOfBytes [in]

Specifies the size, in bytes, of the lookaside-list entry to allocate.


### -param Tag [in]

Specifies the four-byte pool tag to use to mark the allocated storage for the new lookaside-list entry. For more information about pool tags, see the description of the <i>Tag</i> parameter in <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. 


### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes the lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine. 


## -returns
<i>LookasideListAllocateEx</i> returns a pointer to the allocated lookaside-list entry. If the routine cannot allocate an entry, it returns <b>NULL</b>. 


## -remarks
A driver that creates a lookaside list can implement a <i>LookasideListAllocateEx</i> routine to dynamically allocate buffers for the list. A buffer that is not in use is stored as an entry in the list. All entries in a lookaside list are buffers of a uniform size, which the driver specifies when the list is initialized.

The driver supplies a pointer to a custom <i>LookasideListAllocateEx</i> routine as an input parameter in the <b>ExInitializeLookasideListEx</b> call that initializes the lookaside list. If the driver sets this parameter to <b>NULL</b>, the lookaside list uses a default allocation routine instead.

A driver calls the <a href="..\wdm\nf-wdm-exallocatefromlookasidelistex.md">ExAllocateFromLookasideListEx</a> routine to allocate an entry from a lookaside list. If the list is empty (contains no entries), <b>ExAllocateFromLookasideListEx</b> calls <i>LookasideListAllocateEx</i> to dynamically allocate the storage for a new entry. <i>LookasideListAllocateEx</i> returns a pointer to the newly allocated entry if the allocation is successful. Otherwise, it returns <b>NULL</b>.

The <i>PoolType</i>, <i>NumberOfBytes</i>, <i>Tag</i>, and <i>Lookaside</i> parameters contain the same values that were passed as input parameters in the <b>ExInitializeLookasideListEx</b> call that initialized the lookaside list.

The <i>LookasideListAllocateEx</i> routine can use the <i>Lookaside</i> parameter to access private context data that the driver has associated with the lookaside list. For more information, see the code example in <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

The <i>LookasideListAllocateEx</i> routine is called at the same IRQL as the call to <b>ExAllocateFromLookasideListEx</b> that requests the entry. For a call that requests an entry that resides in paged memory, the caller must be running IRQL &lt;= APC_LEVEL. For a call that requests an entry that resides in nonpaged memory, the caller must be running IRQL &lt;= DISPATCH_LEVEL. 

To define a <i>LookasideListAllocateEx</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>LookasideListAllocateEx</i> callback routine that is named <code>MyLookasideListAllocateEx</code>, use the FREE_FUNCTION_EX type as shown in this code example:

Then, implement your callback routine as follows:

The FREE_FUNCTION_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the FREE_FUNCTION_EX function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatefromlookasidelistex.md">ExAllocateFromLookasideListEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20LookasideListAllocateEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

