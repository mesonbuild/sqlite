project('sqlite', 'c', version : '3140200', license : 'pd')


thread_dep = dependency('threads')
sqlite3_dep = dependency('sqlite3')

cc = meson.get_compiler('c')
dl_dep = cc.find_library('dl', required: false)


sqinc = include_directories('.')
sqlib = library('sqlite', 'sqlite3.c', include_directories: sqinc,
    dependencies : [thread_dep, sqlite3_dep, dl_dep])


sqlite_dep = declare_dependency(link_with : sqlib,
    include_directories : sqinc)
