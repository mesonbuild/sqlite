project('sqlite', 'c')

if get_option('shared_lib')
  sqlib = static_library('sqlite', 'sqlite3.c')
else
  sqlib = shared_library('sqlite', 'sqlite3.c')
endif

sqinc = include_directories('.')
