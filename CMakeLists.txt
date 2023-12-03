cmake_minimum_required (VERSION 3.27.2)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project (
	"Blades-of-Exile-Fixes-Only"
	VERSION 0.0.1
	HOMEPAGE_URL "https://github.com/CorrodedCoder/Blades-of-Exile-Fixes-Only"
	LANGUAGES C
	)

include(cmake/PreventInSourceBuilds.cmake)

if (MSVC)
	# Disable complaints about not using MS's "secure" versions of CRT functions.
	add_definitions(-D_CRT_SECURE_NO_WARNINGS -DNOMINMAX -D_CRT_DECLARE_NONSTDC_NAMES=0)
endif()

add_subdirectory(src)
