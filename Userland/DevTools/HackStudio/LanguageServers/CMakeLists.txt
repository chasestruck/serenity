compile_ipc(LanguageServer.ipc LanguageServerEndpoint.h)
compile_ipc(LanguageClient.ipc LanguageClientEndpoint.h)

set(SOURCES
        ConnectionFromClient.cpp
        FileDB.cpp)
set(GENERATED_SOURCES
        LanguageClientEndpoint.h
        LanguageServerEndpoint.h)

serenity_lib(LibLanguageServer language_server)
target_link_libraries(LibLanguageServer LibCodeComprehension LibC)

add_subdirectory(Cpp)
add_subdirectory(Shell)
