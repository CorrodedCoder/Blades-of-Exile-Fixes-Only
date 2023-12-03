add_executable (Scen-Ed WIN32
	blscened.c
	graphics.c
	edsound.c
	keydlgs.c
	graphutl.c
	tactions.c
	dlogtool.c
	scenario.c
	tfileio.c
	townout_stub.c
	global.c
	buttonmg.c
	BLSCENED.RC
	)

target_link_libraries(Scen-Ed Winmm.lib)
