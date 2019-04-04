project('sqlite', 'c', version : '3250100', license : 'pd')


thread_dep = dependency('threads')

cc = meson.get_compiler('c')
dl_dep = cc.find_library('dl', required: false)

if host_machine.system() == 'windows'
  add_project_arguments('-DSQLITE_API=__declspec(dllexport)', language: 'c')
endif

sqinc = include_directories('.')
sqlib = library('sqlite', 'sqlite3.c', include_directories: sqinc,
    dependencies : [thread_dep, dl_dep])


sqlite_dep = declare_dependency(link_with : sqlib,
    include_directories : sqinc)
