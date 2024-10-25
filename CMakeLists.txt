#
# Copyright 2024 NXP
#
# SPDX-License-Identifier: MIT
#

if (CONFIG_MCUX_COMPONENT_middleware.freertos.coremqtt-agent)
    mcux_add_source(
        SOURCES source/include/core_mqtt_agent.h
                source/include/core_mqtt_agent_command_functions.h
                source/include/core_mqtt_agent_config_defaults.h
                source/include/core_mqtt_agent_default_logging.h
                source/include/core_mqtt_agent_message_interface.h
                source/core_mqtt_agent_command_functions.c
                source/core_mqtt_agent.c
        BASE_PATH ${SdkRootDirPath}/rtos/freertos/coremqtt-agent/
    )
    mcux_add_include(
        INCLUDES source/include
        BASE_PATH ${SdkRootDirPath}/rtos/freertos/coremqtt-agent/
    )

    mcux_add_configuration(
        CC "-DMQTT_AGENT_DO_NOT_USE_CUSTOM_CONFIG"
    )
endif()
