project('sqlite', 'c', version : '3140200', license : 'pd')

sqlib = library('sqlite', 'sqlite3.c')
sqinc = include_directories('.')

sqlite_dep = declare_dependency(link_with : sqlib,
    include_directories : sqinc)
