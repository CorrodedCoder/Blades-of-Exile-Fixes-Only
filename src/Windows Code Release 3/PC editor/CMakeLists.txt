add_executable (PC-editor WIN32
	bladpced.c
	graphics.c
	graphutl.c
	edsound.c
	editors.c
	dlogtool.c
	edfileio.c
	edaction.c
	global.c
	BLADPCED.RC
	)

target_link_libraries(PC-editor Winmm.lib)
