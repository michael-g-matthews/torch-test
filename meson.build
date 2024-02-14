project('example-app', 
    'cpp',
    'cuda',
    default_options: [
        'buildtype=release',
        'cpp_std=c++17'
    ],
)
import('cmake')

torch_dep = dependency('Torch', 
    # version: '>=2.1.2',
    method: 'cmake', 
    # method: 'pkg-config',
    # cmake_args: '-DCMAKE_PREFIX_PATH=/opt/libtorch', 
    fallback:[
        'torch', 
        'libtorch'
    ]
)

executable('example-app',
  ['example-app.cpp'],
  dependencies: torch_dep,
  # include_directories: torch_dep.get_pkgconfig_variable('includedir')
)
