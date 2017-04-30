package(default_visibility = ["//visibility:public"])

# Go boilerplate
load("@io_bazel_rules_go//go:def.bzl", "go_binary")

load("@io_bazel_rules_docker//docker:docker.bzl", "docker_build")

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

docker_build(
    name = "py",
    base = "//base:python27",
    files = [":hello-py.par"],
    cmd = ["/hello-py.par"],
)

load("@io_bazel_rules_rust//rust:rust.bzl", "rust_binary")

rust_binary(
    name = "hello_rust",
    srcs = ["main.rs"],
)

docker_build(
    name = "rust",
    base = "//base:cc",
    files = [":hello_rust"],
    entrypoint = ["/hello_rust"]
)

load("@io_bazel_rules_d//d:d.bzl", "d_binary")

d_binary(
    name = "hello-d",
    srcs = ["main.d"],
)

docker_build(
    name = "d",
    base = "//base:cc",
    files = [":hello-d"],
    entrypoint = ["/hello-d"]
)
