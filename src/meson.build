sources = ['memorylatency.c']

binary_suffix = ''

m5_build_path = '' + get_option('m5_build_path')
gem5_include_dir = '' + get_option('gem5_include_dir')
if (m5_build_path != '') and (gem5_include_dir != '')
  binary_suffix += '.m5'
endif

executable('memorylatency' + binary_suffix,
           sources,
           c_args: default_cflags,
           link_args: default_ldflags + ['-lm'],
           install : true)
