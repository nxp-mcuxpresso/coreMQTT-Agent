#
# Copyright 2024-2026 NXP
#
# SPDX-License-Identifier: BSD-3-Clause
#

if (CONFIG_MCUX_COMPONENT_middleware.freertos.coremqtt-agent)
    mcux_add_source(
        SOURCES ../coremqtt-agent-upstream/source/include/core_mqtt_agent.h
                ../coremqtt-agent-upstream/source/include/core_mqtt_agent_command_functions.h
                ../coremqtt-agent-upstream/source/include/core_mqtt_agent_config_defaults.h
                ../coremqtt-agent-upstream/source/include/core_mqtt_agent_default_logging.h
                ../coremqtt-agent-upstream/source/include/core_mqtt_agent_message_interface.h
                ../coremqtt-agent-upstream/source/core_mqtt_agent_command_functions.c
                ../coremqtt-agent-upstream/source/core_mqtt_agent.c
    )
    mcux_add_include(
        INCLUDES ../coremqtt-agent-upstream/source/include
    )

    mcux_add_configuration(
        CC "-DMQTT_AGENT_DO_NOT_USE_CUSTOM_CONFIG"
    )
endif()
