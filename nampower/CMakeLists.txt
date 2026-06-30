set(DLL_NAME nampower)

include_directories(Include ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_SOURCE_DIR})

set(SOURCE_FILES
        types.h
        logging.hpp
        logging.cpp
        cdatastore.hpp
        cdatastore.cpp
        castqueue.h
        cooldown.hpp
        game.hpp
        game.cpp
        main.hpp
        main.cpp
        chat.hpp
        chat.cpp
        offsets.hpp
        helper.cpp
        helper.hpp
        spellcast.hpp
        spellcast.cpp
        spellchannel.hpp
        spellchannel.cpp
        spellevents.hpp
        spellevents.cpp
        misc_scripts.hpp
        misc_scripts.cpp
        file_scripts.hpp
        file_scripts.cpp
        spell_scripts.hpp
        spell_scripts.cpp
        cooldown_scripts.hpp
        cooldown_scripts.cpp
        item_scripts.hpp
        item_scripts.cpp
        items.hpp
        items.cpp
        dbc_fields.hpp
        dbc_fields.cpp
        unit_fields.hpp
        unit_fields.cpp
        party_member_fields.hpp
        party_member_fields.cpp
        auras.hpp
        auras.cpp
        lua_refs.hpp
        lua_refs.cpp
        autoattack.hpp
        autoattack.cpp
        player_scripts.hpp
        player_scripts.cpp
        unit_scripts.hpp
        unit_scripts.cpp
        pet.hpp
        pet.cpp
        unit.hpp
        unit.cpp
        tooltip.hpp
        tooltip.cpp
        quest.hpp
        quest.cpp
)

add_library(${DLL_NAME} SHARED ${SOURCE_FILES})
target_link_libraries(${DLL_NAME} shlwapi.lib asmjit.lib udis86.lib)

# Generate MAP file for debugging crashes
target_link_options(${DLL_NAME} PRIVATE /MAP)

install(TARGETS ${DLL_NAME} RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}")
