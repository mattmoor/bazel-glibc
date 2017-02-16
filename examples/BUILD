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
