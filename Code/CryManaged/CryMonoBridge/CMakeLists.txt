#START-FILE-LIST
# File List auto generated by waf2cmake.py, do not modify manually.

start_sources()
# -- crymonobridge.waf_files --
sources_platform(ALL)
add_sources("CryMonoBridge_main_uber_1.cpp"
	SOURCE_GROUP "Root"
		"CryMonoBridge.h"
		"CryMonoBridge.cpp"
		"MonoRuntime.h"
		"MonoRuntime.cpp"
		"MonoLibrary.h"
		"MonoLibrary.cpp"
		"resource.h"
		"StdAfx.h"
)

add_sources("NoUberFile"
	SOURCE_GROUP "Root"
		"StdAfx.cpp"
	SOURCE_GROUP "SWIG"
		"SWIG/CryEngine.swig"
		"SWIG/CryAction.i"
		"SWIG/Cry3DEngine.i"
		"SWIG/CryAISystem.i"
		"SWIG/CryAnimation.i"
		"SWIG/CryAudio.i"
		"SWIG/CryCommon.i"
		"SWIG/CryDynamicResponseSystem.i"
		"SWIG/CryEntitySystem.i"
		"SWIG/CryFont.i"
		"SWIG/CryGame.i"
		"SWIG/CryInput.i"
		"SWIG/CryMonoBridge.i"
		"SWIG/CryLiveCreate.i"
		"SWIG/CryLobby.i"
		"SWIG/CryMovie.i"
		"SWIG/CryNetwork.i"
		"SWIG/CryPhysics.i"
		"SWIG/CryRender.i"
		"SWIG/CryScriptSystem.i"
		"SWIG/CrySystem.i"
		"SWIG/ForwardDeclarations.i"
)

end_sources()
#END-FILE-LIST

CryEngineModule(CryMonoBridge PCH "StdAfx.cpp" SOLUTION_FOLDER "CryEngine")
target_compile_options(${THIS_PROJECT} PRIVATE /EHsc /bigobj)
target_include_directories(${THIS_PROJECT} PRIVATE ${CMAKE_SOURCE_DIR}/Code/CryEngine/CryAction )
target_compile_definitions(${THIS_PROJECT} PRIVATE -DPy_BUILD_CORE)
if(WIN32)
	use_mono()
	target_link_libraries(${THIS_PROJECT} PRIVATE Shell32)
endif()
