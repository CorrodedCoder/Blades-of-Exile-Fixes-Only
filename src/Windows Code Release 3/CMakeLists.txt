
add_executable (Blades-of-Exile WIN32
	blades.c
	graphics.c
	newgraph.c
	fileio.c
	actions.c
	text.c
	party.c
	exlsound.c
	items.c
	fields.c
	town.c
	startup.c
	dlogtool.c
	dlgutils.c
	infodlgs.c
	graphutl.c
	global.c
	gutils.c
	monster.c
	locutils.c
	itemdata.c
	combat.c
	townspec.c
	specials.c
	
	BLADES.RC
	GAMEDLOG.RC
	GAMESTR.RC
	)

target_link_libraries(Blades-of-Exile Winmm.lib)

add_custom_command(
        TARGET Blades-of-Exile POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory
               "${CMAKE_CURRENT_SOURCE_DIR}/Scen Ed"
               "${CMAKE_CURRENT_BINARY_DIR}/blscened")

add_custom_command(
        TARGET Blades-of-Exile POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory
               "${CMAKE_CURRENT_SOURCE_DIR}/BLADSCEN"
               "${CMAKE_CURRENT_BINARY_DIR}/bladscen")

add_subdirectory("PC Editor")
add_subdirectory("Scen Ed")
