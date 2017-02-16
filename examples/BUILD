package(default_visibility = ["//visibility:public"])

# Go boilerplate
load("@io_bazel_rules_go//go:def.bzl", "go_binary")

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

go_binary(
    name = "hello",
    srcs = ["main.go"],
)

docker_build(
    name = "image",
    base = "//:glibc",
    files = [":hello"],
    entrypoint = ["/hello"]
)
