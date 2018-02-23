---
UID: NA:pep_x
ms.assetid: 58bb1f9b-0265-3590-af11-186f988fd807
ms.author: windowsdriverdev
ms.date: 01/18/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# pep_x.h header



pep_x.h contains the following programming interfaces:





## Functions
| Title | Description |
| ---- |:---- |
| [PEPCALLBACKNOTIFYACPI](nc-pep_x-pepcallbacknotifyacpi.md) | An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYDPM](nc-pep_x-pepcallbacknotifydpm.md) | An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYPPM](nc-pep_x-pepcallbacknotifyppm.md) | An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKPOWERONCRASHDUMPDEVICE](nc-pep_x-pepcallbackpoweroncrashdumpdevice.md) | The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device. |
| [POFXCALLBACKCRITICALRESOURCE](nc-pep_x-pofxcallbackcriticalresource.md) | The TransitionCriticalResource routine changes the active/inactive state of a core system component. |
| [POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS](nc-pep_x-pofxcallbackenumerateunmaskedinterrupts.md) | The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled. |
| [POFXCALLBACKPLATFORMIDLEVETO](nc-pep_x-pofxcallbackplatformidleveto.md) | The PlatformIdleVeto routine increments or decrements the veto count for a veto code for a platform idle state. |
| [POFXCALLBACKPROCESSORHALT](nc-pep_x-pofxcallbackprocessorhalt.md) | The ProcessorHalt routine prepares the processor to be halted. |
| [POFXCALLBACKPROCESSORIDLEVETO](nc-pep_x-pofxcallbackprocessoridleveto.md) | The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state. |
| [POFXCALLBACKREQUESTCOMMON](nc-pep_x-pofxcallbackrequestcommon.md) | The RequestCommon routine is a generic request handler. |
| [POFXCALLBACKREQUESTINTERRUPT](nc-pep_x-pofxcallbackrequestinterrupt.md) | The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state. |
| [POFXCALLBACKREQUESTWORKER](nc-pep_x-pofxcallbackrequestworker.md) | The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device. |
| [POFXCALLBACKUPDATEPLATFORMIDLESTATE](nc-pep_x-pofxcallbackupdateplatformidlestate.md) | The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state. |
| [POFXCALLBACKUPDATEPROCESSORIDLESTATE](nc-pep_x-pofxcallbackupdateprocessoridlestate.md) | The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state. |
| [PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK](nc-pep_x-ppo_enumerate_interrupt_source_callback.md) | An EnumerateInterruptSource callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source. |
| [PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE](nf-pep_x-pep_acpi_initialize_extended_io_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE](nf-pep_x-pep_acpi_initialize_extended_memory_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE](nf-pep_x-pep_acpi_initialize_gpio_int_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE](nf-pep_x-pep_acpi_initialize_gpio_io_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE](nf-pep_x-pep_acpi_initialize_interrupt_resource.md) | The PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_IOPORT_RESOURCE](nf-pep_x-pep_acpi_initialize_ioport_resource.md) | The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_MEMORY_RESOURCE](nf-pep_x-pep_acpi_initialize_memory_resource.md) | The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE](nf-pep_x-pep_acpi_initialize_spb_i2c_resource.md) | The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE](nf-pep_x-pep_acpi_initialize_spb_spi_resource.md) | The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE](nf-pep_x-pep_acpi_initialize_spb_uart_resource.md) | The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure. |
| [PoFxRegisterCoreDevice](nf-pep_x-pofxregistercoredevice.md) | The PoFxRegisterCoreDevice routine registers a new core system resource with the Windows power management framework (PoFx). |
| [PoFxRegisterPlugin](nf-pep_x-pofxregisterplugin.md) | The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |
| [PoFxRegisterPluginEx](nf-pep_x-pofxregisterpluginex.md) | The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |



## Structures
| Title | Description |
| ---- |:---- |
| [_PEP_ABANDON_DEVICE](ns-pep_x-_pep_abandon_device.md) | The PEP_ABANDON_DEVICE structure identifies a device that has been abandoned and will no longer be used by the operating system. |
| [_PEP_ACPI_ABANDON_DEVICE](ns-pep_x-_pep_acpi_abandon_device.md) | The PEP_ACPI_ABANDON_DEVICE structure indicates whether the platform extension plug-in (PEP) accepts ownership of an abandoned device. |
| [_PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE](ns-pep_x-_pep_acpi_enumerate_device_namespace.md) | The PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure contains an enumeration of the objects in the namespace of the device. |
| [_PEP_ACPI_EVALUATE_CONTROL_METHOD](ns-pep_x-_pep_acpi_evaluate_control_method.md) | The PEP_ACPI_EVALUATE_CONTROL_METHOD structure specifies an ACPI control method to evaluate, an input argument to supply to this method, and an output buffer for the result of the evaluation. |
| [_PEP_ACPI_EXTENDED_ADDRESS](ns-pep_x-_pep_acpi_extended_address.md) | The PEP_ACPI_EXTENDED_ADDRESS structure is used to report resource usage in the address space such as memory and IO. |
| [_PEP_ACPI_GPIO_RESOURCE](ns-pep_x-_pep_acpi_gpio_resource.md) | The PEP_ACPI_GPIO_RESOURCE structure describes the ACPI configuration for a general purpose input/output (GPIO) resource. |
| [_PEP_ACPI_INTERRUPT_RESOURCE](ns-pep_x-_pep_acpi_interrupt_resource.md) | The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource. |
| [_PEP_ACPI_IO_MEMORY_RESOURCE](ns-pep_x-_pep_acpi_io_memory_resource.md) | The PEP_ACPI_IO_MEMORY_RESOURCE structure describes an ACPI IO port descriptor resource. |
| [_PEP_ACPI_OBJECT_NAME](ns-pep_x-_pep_acpi_object_name.md) | The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object. |
| [_PEP_ACPI_OBJECT_NAME_WITH_TYPE](ns-pep_x-_pep_acpi_object_name_with_type.md) | The PEP_ACPI_OBJECT_NAME_WITH_TYPE structure that specifies both the path-relative name of an ACPI object and the type of this object. |
| [_PEP_ACPI_PREPARE_DEVICE](ns-pep_x-_pep_acpi_prepare_device.md) | The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device. |
| [_PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES](ns-pep_x-_pep_acpi_query_device_control_resources.md) | The PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES structure contains a list of raw resources that are needed to control power to the device. |
| [_PEP_ACPI_QUERY_OBJECT_INFORMATION](ns-pep_x-_pep_acpi_query_object_information.md) | The PEP_ACPI_QUERY_OBJECT_INFORMATION structure contains information about an ACPI object. |
| [_PEP_ACPI_REGISTER_DEVICE](ns-pep_x-_pep_acpi_register_device.md) | The PEP_ACPI_REGISTER_DEVICE structure contains registration information about a device for which the platform extension plug-in (PEP) is to provide ACPI services. |
| [_PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES](ns-pep_x-_pep_acpi_request_convert_to_bios_resources.md) | The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions. |
| [_PEP_ACPI_RESOURCE](ns-pep_x-_pep_acpi_resource.md) | The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource. |
| [_PEP_ACPI_RESOURCE_FLAGS](ns-pep_x-_pep_acpi_resource_flags.md) | The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource. |
| [_PEP_ACPI_SPB_I2C_RESOURCE](ns-pep_x-_pep_acpi_spb_i2c_resource.md) | The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource. |
| [_PEP_ACPI_SPB_RESOURCE](ns-pep_x-_pep_acpi_spb_resource.md) | The PEP_ACPI_SPB_RESOURCE structure describes an ACPI serial bus connection resource. |
| [_PEP_ACPI_SPB_SPI_RESOURCE](ns-pep_x-_pep_acpi_spb_spi_resource.md) | The PEP_ACPI_SPB_SPI_RESOURCE structure describes an ACPI SPI serial bus resource. |
| [_PEP_ACPI_SPB_UART_RESOURCE](ns-pep_x-_pep_acpi_spb_uart_resource.md) | The PEP_ACPI_SPB_UART_RESOURCE structure describes an ACPI UART serial bus resource. |
| [_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES](ns-pep_x-_pep_acpi_translated_device_control_resources.md) | The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use. |
| [_PEP_ACPI_UNREGISTER_DEVICE](ns-pep_x-_pep_acpi_unregister_device.md) | The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services. |
| [_PEP_COMPONENT_ACTIVE](ns-pep_x-_pep_component_active.md) | The PEP_COMPONENT_ACTIVE structure identifies a component that is making a transition between the idle condition and the active condition. |
| [_PEP_COMPONENT_PERF_INFO](ns-pep_x-_pep_component_perf_info.md) | The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component. |
| [_PEP_COMPONENT_PERF_SET](ns-pep_x-_pep_component_perf_set.md) | The PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set. |
| [_PEP_COMPONENT_PERF_STATE_REQUEST](ns-pep_x-_pep_component_perf_state_request.md) | The PEP_COMPONENT_PERF_STATE_REQUEST structure specifies a performance state (P-state) set and a new performance level to assign to this set. |
| [_PEP_COMPONENT_PLATFORM_CONSTRAINTS](ns-pep_x-_pep_component_platform_constraints.md) | The PEP_COMPONENT_PLATFORM_CONSTRAINTS structure describes the lowest-powered Fx state of that a component can be in when the platform is in a particular idle state. |
| [_PEP_COMPONENT_V2](ns-pep_x-_pep_component_v2.md) | The PEP_COMPONENT_V2 structure specifies the power state attributes of a component in the device. |
| [_PEP_COORDINATED_DEPENDENCY_OPTION](ns-pep_x-_pep_coordinated_dependency_option.md) | The PEP_COORIDNATED_DEPENDENCY_OPTION structure describes a coordinated idle stateâ€™s dependency to the OS. |
| [_PEP_COORDINATED_IDLE_STATE](ns-pep_x-_pep_coordinated_idle_state.md) | The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS. |
| [_PEP_CRASHDUMP_INFORMATION](ns-pep_x-_pep_crashdump_information.md) | The PEP_CRASHDUMP_INFORMATION structure contains information about a crash-dump device. |
| [_PEP_DEBUGGER_TRANSITION_REQUIREMENTS](ns-pep_x-_pep_debugger_transition_requirements.md) | The PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure indicates the platform idle states for which the debugger device must be turned on. |
| [_PEP_DEVICE_PLATFORM_CONSTRAINTS](ns-pep_x-_pep_device_platform_constraints.md) | The PEP_DEVICE_PLATFORM_CONSTRAINTS structure specifies the constraints for entry to the various Dx power states that are supported by a device. |
| [_PEP_DEVICE_POWER_STATE](ns-pep_x-_pep_device_power_state.md) | The PEP_DEVICE_POWER_STATE structure indicates the status of a transition to a new Dx (device power) state. |
| [_PEP_DEVICE_REGISTER_V2](ns-pep_x-_pep_device_register_v2.md) | The PEP_DEVICE_REGISTER structure describes all the components in a particular device. |
| [_PEP_DEVICE_STARTED](ns-pep_x-_pep_device_started.md) | The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx). |
| [_PEP_INFORMATION](ns-pep_x-_pep_information.md) | The PEP_INFORMATION structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V1](ns-pep_x-_pep_kernel_information_struct_v1.md) | The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V2](ns-pep_x-_pep_kernel_information_struct_v2.md) | The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V3](ns-pep_x-_pep_kernel_information_struct_v3.md) | The PEP_KERNEL_INFORMATION_STRUCT_V3 structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_LOW_POWER_EPOCH](ns-pep_x-_pep_low_power_epoch.md) | The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated). |
| [_PEP_NOTIFY_COMPONENT_IDLE_STATE](ns-pep_x-_pep_notify_component_idle_state.md) | The PEP_NOTIFY_COMPONENT_IDLE_STATE structure contains status information about a component's pending transition to a new Fx power state. |
| [_PEP_PERF_STATE](ns-pep_x-_pep_perf_state.md) | The PEP_PERF_STATE structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values. |
| [_PEP_PLATFORM_IDLE_STATE](ns-pep_x-_pep_platform_idle_state.md) | The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state. |
| [_PEP_PLATFORM_IDLE_STATE_UPDATE](ns-pep_x-_pep_platform_idle_state_update.md) | The PEP_PLATFORM_IDLE_STATE_UPDATE structure contains the updated properties of a platform idle state. |
| [_PEP_POWER_CONTROL_COMPLETE](ns-pep_x-_pep_power_control_complete.md) | The PEP_POWER_CONTROL_COMPLETE structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed. |
| [_PEP_POWER_CONTROL_REQUEST](ns-pep_x-_pep_power_control_request.md) | The PEP_POWER_CONTROL_REQUEST structure contains a request from a driver for a power control operation. |
| [_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE](ns-pep_x-_pep_ppm_context_query_parking_page.md) | The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor. |
| [_PEP_PPM_CST_STATE](ns-pep_x-_pep_ppm_cst_state.md) | The PEP_PPM_CST_STATE structure specifies the properties of a C state (ACPI processor power state). |
| [_PEP_PPM_CST_STATES](ns-pep_x-_pep_ppm_cst_states.md) | The PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor. |
| [_PEP_PPM_ENTER_SYSTEM_STATE](ns-pep_x-_pep_ppm_enter_system_state.md) | Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  . |
| [_PEP_PPM_FEEDBACK_READ](ns-pep_x-_pep_ppm_feedback_read.md) | The PEP_PPM_FEEDBACK_READ structure contains the value read from a processor performance feedback counter. |
| [_PEP_PPM_IDLE_CANCEL](ns-pep_x-_pep_ppm_idle_cancel.md) | The PEP_PPM_IDLE_CANCEL structure indicates why the processor could not enter the previously selected idle state. |
| [_PEP_PPM_IDLE_COMPLETE](ns-pep_x-_pep_ppm_idle_complete.md) | The PEP_PPM_IDLE_COMPLETE structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_COMPLETE_V2](ns-pep_x-_pep_ppm_idle_complete_v2.md) | The PEP_PPM_IDLE_COMPLETE_V2 structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_EXECUTE](ns-pep_x-_pep_ppm_idle_execute.md) | The PEP_PPM_IDLE_EXECUTE structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_EXECUTE_V2](ns-pep_x-_pep_ppm_idle_execute_v2.md) | The PEP_PPM_IDLE_EXECUTE_V2 structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_SELECT](ns-pep_x-_pep_ppm_idle_select.md) | The PEP_PPM_IDLE_SELECT structure describes the most energy-efficient idle state that the processor can enter and still satisfy the constraints specified by the operating system. |
| [_PEP_PPM_INITIATE_WAKE](ns-pep_x-_pep_ppm_initiate_wake.md) | The PEP_PPM_INITIATE_WAKE structure indicates whether a processor requires an interrupt to wake up from an idle state. |
| [_PEP_PPM_IS_PROCESSOR_HALTED](ns-pep_x-_pep_ppm_is_processor_halted.md) | The PEP_PPM_IS_PROCESSOR_HALTED structure indicates whether the processor is currently halted in its selected idle state. |
| [_PEP_PPM_LPI_COMPLETE](ns-pep_x-_pep_ppm_lpi_complete.md) | The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor. |
| [_PEP_PPM_PARK_MASK](ns-pep_x-_pep_ppm_park_mask.md) | The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask. |
| [_PEP_PPM_PARK_SELECTION](ns-pep_x-_pep_ppm_park_selection.md) | The PEP_PPM_PARK_SELECTION structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PARK_SELECTION_V2](ns-pep_x-_pep_ppm_park_selection_v2.md) | The PEP_PPM_PARK_SELECTION_V2 structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PERF_CHECK_COMPLETE](ns-pep_x-_pep_ppm_perf_check_complete.md) | The PEP_PPM_PERF_CHECK_COMPLETE structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation. |
| [_PEP_PPM_PERF_SET](ns-pep_x-_pep_ppm_perf_set.md) | The PEP_PPM_PERF_SET structure specifies the new performance level that the operating system is requesting for the processor. |
| [_PEP_PPM_PERF_SET_STATE](ns-pep_x-_pep_ppm_perf_set_state.md) | Used in the PEP_NOTIFY_PPM_PERF_SET notification at runtime to set the current operating performance of the processor.  . |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCIES](ns-pep_x-_pep_ppm_platform_state_residencies.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform. |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCY](ns-pep_x-_pep_ppm_platform_state_residency.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state. |
| [_PEP_PPM_QUERY_CAPABILITIES](ns-pep_x-_pep_ppm_query_capabilities.md) | The PEP_PPM_QUERY_CAPABILITIES structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP). |
| [_PEP_PPM_QUERY_COORDINATED_DEPENDENCY](ns-pep_x-_pep_ppm_query_coordinated_dependency.md) | The PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure describes dependencies for coordinated idle states. |
| [_PEP_PPM_QUERY_COORDINATED_STATES](ns-pep_x-_pep_ppm_query_coordinated_states.md) | The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PPM_QUERY_DISCRETE_PERF_STATES](ns-pep_x-_pep_ppm_query_discrete_perf_states.md) | Used in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES notification that stores the list of discrete performance states that PEP supports, if the PEP_NOTIFY_PPM_QUERY_CAPABILITIES notification indicates support for discrete performance states. . |
| [_PEP_PPM_QUERY_DOMAIN_INFO](ns-pep_x-_pep_ppm_query_domain_info.md) | Used in the PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO notification that queries for information about a performance domain. . |
| [_PEP_PPM_QUERY_FEEDBACK_COUNTERS](ns-pep_x-_pep_ppm_query_feedback_counters.md) | The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor. |
| [_PEP_PPM_QUERY_IDLE_STATES](ns-pep_x-_pep_ppm_query_idle_states.md) | The PEP_PPM_QUERY_IDLE_STATES structure describes the idle states of a particular processor. |
| [_PEP_PPM_QUERY_IDLE_STATES_V2](ns-pep_x-_pep_ppm_query_idle_states_v2.md) | The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports. |
| [_PEP_PPM_QUERY_LP_SETTINGS](ns-pep_x-_pep_ppm_query_lp_settings.md) | The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario. |
| [_PEP_PPM_QUERY_PERF_CAPABILITIES](ns-pep_x-_pep_ppm_query_perf_capabilities.md) | The PEP_PPM_QUERY_PERF_CAPABILITIES structure describes the performance capabilities of the processors in the specified processor performance domain. |
| [_PEP_PPM_QUERY_PERF_CONSTRAINTS](ns-pep_x-_pep_ppm_query_perf_constraints.md) | The PEP_PPM_PERF_CONSTRAINTS structure describes the performance limits to apply to the processor. |
| [_PEP_PPM_QUERY_PLATFORM_STATE](ns-pep_x-_pep_ppm_query_platform_state.md) | The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state. |
| [_PEP_PPM_QUERY_PLATFORM_STATES](ns-pep_x-_pep_ppm_query_platform_states.md) | The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports. |
| [_PEP_PPM_QUERY_STATE_NAME](ns-pep_x-_pep_ppm_query_state_name.md) | The PEP_PPM_QUERY_STATE_NAME structure contains information about a specific coordinated or platform idle state. |
| [_PEP_PPM_QUERY_VETO_REASON](ns-pep_x-_pep_ppm_query_veto_reason.md) | The PEP_PPM_QUERY_VETO_REASON structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason. |
| [_PEP_PPM_QUERY_VETO_REASONS](ns-pep_x-_pep_ppm_query_veto_reasons.md) | The PEP_PPM_QUERY_VETO_REASONS structure specifies the total number of veto reasons that the PEP uses in calls to the ProcessorIdleVeto and PlatformIdleVeto routines. |
| [_PEP_PPM_RESUME_FROM_SYSTEM_STATE](ns-pep_x-_pep_ppm_resume_from_system_state.md) | Used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state. |
| [_PEP_PPM_TEST_IDLE_STATE](ns-pep_x-_pep_ppm_test_idle_state.md) | The PEP_PPM_TEST_IDLE_STATE structure contains information about whether the processor can immediately enter a processor idle state. |
| [_PEP_PREPARE_DEVICE](ns-pep_x-_pep_prepare_device.md) | The PEP_PREPARE_DEVICE structure identifies a device that must be started up in preparation for its use by the operating system. |
| [_PEP_PROCESSOR_FEEDBACK_COUNTER](ns-pep_x-_pep_processor_feedback_counter.md) | The PEP_PROCESSOR_FEEDBACK_COUNTER structure describes a feedback counter to the operating system. |
| [_PEP_PROCESSOR_IDLE_CONSTRAINTS](ns-pep_x-_pep_processor_idle_constraints.md) | The PEP_PROCESSOR_IDLE_CONSTRAINTS structure specifies a set of constraints that the PEP uses to select a processor idle state. |
| [_PEP_PROCESSOR_IDLE_DEPENDENCY](ns-pep_x-_pep_processor_idle_dependency.md) | The PEP_PROCESSOR_IDLE_DEPENDENCY structure specifies the dependencies of a platform idle state on the specified processor. |
| [_PEP_PROCESSOR_IDLE_STATE](ns-pep_x-_pep_processor_idle_state.md) | The PEP_PROCESSOR_IDLE_STATE structure describes the capabilities of a processor idle state. |
| [_PEP_PROCESSOR_IDLE_STATE_UPDATE](ns-pep_x-_pep_processor_idle_state_update.md) | The PEP_PROCESSOR_IDLE_STATE_UPDATE structure contains the updated properties of a processor idle state. |
| [_PEP_PROCESSOR_IDLE_STATE_V2](ns-pep_x-_pep_processor_idle_state_v2.md) | The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PROCESSOR_PARK_PREFERENCE](ns-pep_x-_pep_processor_park_preference.md) | The PEP_PROCESSOR_PARK_PREFERENCE structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption. |
| [_PEP_PROCESSOR_PARK_STATE](ns-pep_x-_pep_processor_park_state.md) | The PEP_PROCESSOR_PARK_STATE structure describes the parking state for a single processor. |
| [_PEP_PROCESSOR_PERF_STATE](ns-pep_x-_pep_processor_perf_state.md) | Use in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES  notification. This structure describes the properties of a single performance state.  . |
| [_PEP_QUERY_COMPONENT_PERF_CAPABILITIES](ns-pep_x-_pep_query_component_perf_capabilities.md) | The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET](ns-pep_x-_pep_query_component_perf_set.md) | The PEP_QUERY_COMPONENT_PERF_SET structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET_NAME](ns-pep_x-_pep_query_component_perf_set_name.md) | The PEP_QUERY_COMPONENT_PERF_SET_NAME structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_STATES](ns-pep_x-_pep_query_component_perf_states.md) | The PEP_QUERY_COMPONENT_PERF_STATES structure contains a list of discrete performance state (P-state) values for the specified P-state set. |
| [_PEP_QUERY_CURRENT_COMPONENT_PERF_STATE](ns-pep_x-_pep_query_current_component_perf_state.md) | The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set. |
| [_PEP_QUERY_SOC_SUBSYSTEM](ns-pep_x-_pep_query_soc_subsystem.md) | The PEP_QUERY_SOC_SUBSYSTEM structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM notification to gather basic information about a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME](ns-pep_x-_pep_query_soc_subsystem_blocking_time.md) | The PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification to collect details about the blocking duration for a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM_COUNT](ns-pep_x-_pep_query_soc_subsystem_count.md) | The PEP_QUERY_SOC_SUBSYSTEM_COUNT structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state. |
| [_PEP_QUERY_SOC_SUBSYSTEM_METADATA](ns-pep_x-_pep_query_soc_subsystem_metadata.md) | The PEP_QUERY_SOC_SUBSYSTEM_METADATA structure is used with the PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried. |
| [_PEP_REGISTER_COMPONENT_PERF_STATES](ns-pep_x-_pep_register_component_perf_states.md) | The PEP_REGISTER_COMPONENT_PERF_STATES structure describes the performance states (P-states) of the specified component. |
| [_PEP_REGISTER_CRASHDUMP_DEVICE](ns-pep_x-_pep_register_crashdump_device.md) | The PEP_REGISTER_CRASHDUMP_DEVICE structure provides a callback routine to turn on a crash-dump device. |
| [_PEP_REGISTER_DEBUGGER](ns-pep_x-_pep_register_debugger.md) | The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport. |
| [_PEP_REGISTER_DEVICE_V2](ns-pep_x-_pep_register_device_v2.md) | The PEP_REGISTER_DEVICE_V2 structure describes a device whose driver stack has just registered with the Windows power management framework (PoFx). |
| [_PEP_REQUEST_COMPONENT_PERF_STATE](ns-pep_x-_pep_request_component_perf_state.md) | The PEP_REQUEST_COMPONENT_PERF_STATE structure contains a list of performance state (P-state) changes requested by the Windows power management framework (PoFx), plus status information about the handling of these requests by the platform extension plug-in (PEP). |
| [_PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING](ns-pep_x-_pep_reset_soc_subsystem_accounting.md) | The PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure is provided to the platform extension plug-in (PEP) as part of a PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification. |
| [_PEP_SOC_SUBSYSTEM_METADATA](ns-pep_x-_pep_soc_subsystem_metadata.md) | The PEP_SOC_SUBSYSTEM_METADATA structure contains key-value pairs that contain metadata for a system on a chip (SoC) subsystem. It is used in the context of a PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification sent to a platform extension plug-in (PEP). |
| [_PEP_SYSTEM_LATENCY](ns-pep_x-_pep_system_latency.md) | The PEP_SYSTEM_LATENCY structure specifies the new value for the system latency tolerance. |
| [_PEP_UNMASKED_INTERRUPT_FLAGS](ns-pep_x-_pep_unmasked_interrupt_flags.md) | The PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt. |
| [_PEP_UNMASKED_INTERRUPT_INFORMATION](ns-pep_x-_pep_unmasked_interrupt_information.md) | The PEP_UNMASKED_INTERRUPT_INFORMATION structure contains information about an interrupt source. |
| [_PEP_UNREGISTER_DEVICE](ns-pep_x-_pep_unregister_device.md) | The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx). |
| [_PEP_WORK](ns-pep_x-_pep_work.md) | The PEP_WORK structure indicates whether the PEP has a work request to submit to the Windows power management framework (PoFx). |
| [_PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE](ns-pep_x-_pep_work_acpi_evaluate_control_method_complete.md) | The PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP). |
| [_PEP_WORK_ACPI_NOTIFY](ns-pep_x-_pep_work_acpi_notify.md) | The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event. |
| [_PEP_WORK_ACTIVE_COMPLETE](ns-pep_x-_pep_work_active_complete.md) | The PEP_WORK_ACTIVE_COMPLETE structure identifies a component that is now in the active condition. |
| [_PEP_WORK_COMPLETE_IDLE_STATE](ns-pep_x-_pep_work_complete_idle_state.md) | The PEP_WORK_COMPLETE_IDLE_STATE structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new Fx power state. |
| [_PEP_WORK_COMPLETE_PERF_STATE](ns-pep_x-_pep_work_complete_perf_state.md) | The PEP_WORK_COMPLETE_PERF_STATE structure describes the completion status of a previously requested update to the performance values assigned to a list of performance state (P-state) sets. |
| [_PEP_WORK_DEVICE_IDLE](ns-pep_x-_pep_work_device_idle.md) | The PEP_WORK_DEVICE_IDLE structure indicates whether to ignore the idle time-out for the specified device. |
| [_PEP_WORK_DEVICE_POWER](ns-pep_x-_pep_work_device_power.md) | The PEP_WORK_DEVICE_POWER structure describes the new power requirements for the specified device. |
| [_PEP_WORK_IDLE_STATE](ns-pep_x-_pep_work_idle_state.md) | The PEP_WORK_IDLE_STATE structure contains a request to transition a component to an Fx power state. |
| [_PEP_WORK_INFORMATION](ns-pep_x-_pep_work_information.md) | The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx). |
| [_PEP_WORK_POWER_CONTROL](ns-pep_x-_pep_work_power_control.md) | The PEP_WORK_POWER_CONTROL structure contains the parameters for a power control request that the platform extension plug-in (PEP) sends directly to a processor driver. |
| [_PO_FX_CORE_DEVICE](ns-pep_x-_po_fx_core_device.md) | The PO_FX_CORE_DEVICE structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components. |


## Enumerations
| Title | Description |
| ---- |:---- |
| [_GPIO_PIN_CONFIG_TYPE](ne-pep_x-_gpio_pin_config_type.md) | The GPIO_PIN_CONFIG_TYPE enumeration describes a connection IO resource. |
| [_GPIO_PIN_IORESTRICTION_TYPE](ne-pep_x-_gpio_pin_iorestriction_type.md) | The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing. |
| [_PEP_ACPI_OBJECT_TYPE](ne-pep_x-_pep_acpi_object_type.md) | The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object. |
| [_PEP_ACPI_RESOURCE_TYPE](ne-pep_x-_pep_acpi_resource_type.md) | The PEP_ACPI_RESOURCE_TYPE enumeration is used to identify the type of ACPI resource that is contained in the PEP_ACPI_RESOURCE union. |
| [_PEP_DEVICE_ACCEPTANCE_TYPE](ne-pep_x-_pep_device_acceptance_type.md) | The PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device. |
| [_PEP_PERF_STATE_TYPE](ne-pep_x-_pep_perf_state_type.md) | The PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component. |
| [_PEP_PERF_STATE_UNIT](ne-pep_x-_pep_perf_state_unit.md) | The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified. |
| [_PEP_WORK_TYPE](ne-pep_x-_pep_work_type.md) | The PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting. |
| [*PPEP_PROCESSOR_IDLE_CANCEL_CODE](ne-pep_x-ppep_processor_idle_cancel_code.md) | The PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration values indicate reasons why a processor cannot enter an idle state that was previously selected by the platform extension plug-in (PEP). |
| [*PPEP_PROCESSOR_IDLE_TYPE](ne-pep_x-ppep_processor_idle_type.md) | The PEP_PROCESSOR_IDLE_TYPE enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform. |