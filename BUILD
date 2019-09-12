load("@buckaroo//:defs.bzl", "buckaroo_workspace")

a = "@" + buckaroo_workspace("github.com/njlr/bazel-test-a") + "//:a"
b = "@" + buckaroo_workspace("github.com/njlr/bazel-test-b") + "//:b"

cc_library(
  name = "c",
  includes = [
    "include",
  ],
  hdrs = glob([
    "include/*.hpp",
  ]),
  srcs = glob([
    "include/*.hpp",
    "src/*.cpp",
  ]),
  deps = [
    a,
    b,
  ],
  visibility = [
    "//visibility:public",
  ],
)

cc_binary(
  name = "app",
  srcs = [
    "main.cpp",
  ],
  deps = [
    a,
    b,
    ":c",
  ],
)
