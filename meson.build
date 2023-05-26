project('memorylatency', 'c',
  version : '0.3.2',
  license : 'Apache-2.0',
  default_options : ['warning_level=3'])

default_cflags = [
  '-O3', 
  '-Dver="' + meson.project_version() + '"',
  '-Darch="' + host_machine.cpu() + '"',
  '-Dplat="' + host_machine.system() + '"',
  ]

default_ldflags = []

m5_build_path = '' + get_option('m5_build_path')
gem5_include_dir = '' + get_option('gem5_include_dir')
message_prefix = '******************** '
if (m5_build_path != '') and (gem5_include_dir != '')
  message(message_prefix + 'Building the binary with gem5 annotations.')
  default_cflags += ['-DGEM5_ANNOTATION=1']
  default_cflags += ['-I' + gem5_include_dir]
  default_ldflags += ['-L' + m5_build_path]
  default_ldflags += ['-lm5']
else
  message(message_prefix + 'Building the binary without gem5 annotations.')
  if ((m5_build_path != '') or (gem5_include_dir != ''))
    message(message_prefix + 'Building with gem5 annotations is only available if both m5_build_path and gem5_include_dir are non-empty.')
  endif
endif

subdir('src')
