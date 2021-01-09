project('sqlite',
        'c',
        license : 'pd',
        meson_version : '>=0.46',
        version : '3320300')

thread_dep = dependency('threads')

cc = meson.get_compiler('c')
dl_dep = cc.find_library('dl', required : false)
m_dep = cc.find_library('m', required: false)

sqlite_args = []
if cc.get_id() == 'msvc' and get_option('default_library') != 'static'
  sqlite_args += ['-DSQLITE_API=__declspec(dllexport)']
endif

sqinc = include_directories('.')
sqlib = library('sqlite3', 'sqlite3.c', include_directories: sqinc,
    c_args : sqlite_args,
    dependencies : [thread_dep, dl_dep, m_dep],
    # ABI compatibility with autotools/libtool
    version: '0.8.6',
    install: true)

install_headers('sqlite3.h')

sqlite_dep = declare_dependency(link_with : sqlib,
    include_directories : sqinc)

pkg = import('pkgconfig')
pkg.generate(sqlib,
             name: 'sqlite3',
             description: 'An embedded SQL database engine',
             version: meson.project_version())
