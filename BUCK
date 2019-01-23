load('//:buckaroo_macros.bzl', 'buckaroo_deps_from_package')

libuv = buckaroo_deps_from_package('github.com/buckaroo-pm/libuv')

core_foundation = buckaroo_deps_from_package('github.com/buckaroo-pm/libuv')

cxx_library(
  name = 'hiredis',
  header_namespace = 'hiredis',
  exported_headers = glob([
    'adapters/*.h',
    '*.h',
  ]),
  srcs = glob([
    '*.c',
  ], exclude = [
    'test.c',
  ]),
  platform_deps = [
    ('linux.*', libuv),
    ('macos.*', core_foundation),
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'test',
  srcs = [
    'test.c',
  ],
  deps = [
    ':hiredis',
  ],
)
