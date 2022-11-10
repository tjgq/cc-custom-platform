constraint_setting(
  name = "universal_setting",
)

constraint_value(
  name = "universal",
  constraint_setting = ":universal_setting",
  visibility = ["//visibility:public"],
)

platform(
  name = "exec_platform",
  constraint_values = [":universal"],
)

platform(
  name = "target_platform",
  constraint_values = ["@platforms//os:macos", "@platforms//cpu:x86_64"],
)

toolchain(
  name = "cc_toolchain",
  exec_compatible_with = [":universal"],
  target_compatible_with = [":universal"],
  toolchain_type = "@bazel_tools//tools/cpp:toolchain_type",
  toolchain = "@local_config_cc//:cc-compiler-darwin",
)

cc_binary(
  name = "main",
  srcs = ["main.cc"],
)
