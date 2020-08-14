project('CRCpp', 'cpp', 
  version: '1.0.1.0',
  license: 'BSD',
  default_options : ['warning_level=3', 'cpp_std=c++11']
)

crcpp_dep = declare_dependency(
  include_directories: include_directories('inc')
)

if not meson.is_subproject()
  install_headers('inc/CRC.h')
  
  pkgc = import('pkgconfig')
  pkgc.generate(name: 'CRCpp',
    version: meson.project_version(),
    description: 'Easy to use and fast C++ CRC library'
  )
endif
