project('CRCpp', 'cpp', 
  version: '1.0.1.0',
  license: 'BSD',
  default_options : ['warning_level=3', 'cpp_std=c++11']
)

option_args = []

if get_option('CRCPP_USE_NAMESPACE')
  option_args += ['-DCRCPP_USE_NAMESPACE']
endif

if get_option('CRCPP_BRANCHLESS')
  option_args += ['-DCRCPP_BRANCHLESS']
endif

if get_option('CRCPP_USE_CPP11')
  option_args += ['-DCRCPP_USE_CPP11']
endif

if get_option('CRCPP_INCLUDE_ESOTERIC_CRC_DEFINITIONS')
  option_args += ['-DCRCPP_INCLUDE_ESOTERIC_CRC_DEFINITIONS']
endif

crcpp_dep = declare_dependency(
  include_directories: include_directories('inc'),
  compile_args : option_args,
)

if not meson.is_subproject()
  install_headers('inc/CRC.h')

  pkgc = import('pkgconfig')
  pkgc.generate(
    name : 'CRCpp',
    version : meson.project_version(),
    description : 'Easy to use and fast C++ CRC library',
  )
endif
