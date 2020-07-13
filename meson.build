project('sqlite', 'c', version : '3320300', license : 'pd')


thread_dep = dependency('threads')

cc = meson.get_compiler('c')
dl_dep = cc.find_library('dl', required : false)

sqlite_args = []
if cc.get_id() == 'msvc' and get_option('default_library') != 'static'
  sqlite_args += ['-DSQLITE_API=__declspec(dllexport)']
endif

sqinc = include_directories('.')
sqlib = library('sqlite', 'sqlite3.c', include_directories : sqinc,
    c_args : sqlite_args,
    dependencies : [thread_dep, dl_dep], install : true)


sqlite_dep = declare_dependency(link_with : sqlib,
    include_directories : sqinc)
