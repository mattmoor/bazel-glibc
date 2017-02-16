package(default_visibility = ["//visibility:public"])

# Go boilerplate
load("@io_bazel_rules_go//go:def.bzl", "go_binary")

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

go_binary(
    name = "hello-go",
    srcs = ["main.go"],
)

docker_build(
    name = "go",
    base = "//base",
    files = [":hello-go"],
    entrypoint = ["/hello-go"]
)

cc_binary(
    name = "hello-cc",
    srcs = ["main.cc"],
)

docker_build(
    name = "cc",
    base = "//base:cc",
    files = [":hello-cc"],
    entrypoint = ["/hello-cc"]
)

load("@subpar//:subpar.bzl", "par_binary")

par_binary(
    name = "hello-py",
    srcs = ["main.py"],
    main = "main.py",
)

# TODO(mattmoor): We need a hermetic par.
# docker_build(
#     name = "py",
#     base = "//base",
#     files = [":hello-py.par"],
#     entrypoint = ["/hello-py.par"]
# )
