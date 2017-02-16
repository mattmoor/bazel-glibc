package(default_visibility = ["//visibility:public"])

# Go boilerplate
load("@io_bazel_rules_go//go:def.bzl", "go_prefix")
go_prefix("github.com/mattmoor/bazel-glibc")

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

docker_build(
    name = "glibc",
    debs = ["@glibc//file"],
)
