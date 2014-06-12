#!/usr/bin/env python
#coding:gbk
#Copyright (C) dirlt

import glob
import os
env=Environment(CPPPATH=['..'],
                CXXFLAGS='-W -Wall -g -Werror -O2 -Wno-unused-parameter -Wno-unused-function')
env.StaticLibrary('itachi',Glob('*.cc'))

test_env = env.Clone()
test_env.Append(LIBPATH = ['.','../common/'])
test_env.Append(LIBS = ['itachi',
                        'common',
                        'ev',
                        'rt',
                        'pthread'])
for cc in glob.glob('test/*.cc'):
    test_env.Program(os.path.splitext(cc)[0] + '.exe', [cc])
